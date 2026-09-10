# Engineering plan

Status: proposed implementation plan, September 10, 2026. No application work has begun. `PRODUCT.md` governs product rules; this document proposes how to deliver them.

## Objective and first release

Build a comfortable, trustworthy writing environment for essays, creative writing, and fanfiction, then connect it to a readable publishing platform. Compulsory native composition makes editor quality the critical path.

The first engineering milestone is a private editor proof. A small writer alpha follows once server persistence and permissions are dependable. Public launch and all 37 additional Figma screens are not the first milestone.

## Confirmed constraints

- No generative product features. Permit ordinary spelling corrections and transcription of the writer's speech.
- Compose stories/chapters inside the editor, with copy/paste disabled there. Allow normal clipboard use in biographies/comments. Provide dedicated manuscript export.
- Support reliable saving/recovery, native revision, personal comfort, lightweight organization, and real-world input.
- Text-only initially; support future schema evolution for media without building uploads now.
- Owner backend access, no dedicated admin portal initially.
- Thirty-day retention; deleted-draft recovery is the current interpretation. Active work must not expire.

## Proposed technical direction

These are candidates to validate and record in architecture decisions, not already selected technologies.

| Area | Starting direction | Validation before commitment |
| --- | --- | --- |
| Client/application | TypeScript web application with a React editor UI and server-rendered public reading pages | Choose framework, runtime, and deployment compatibility; record versions and commands |
| Editor | Tiptap/ProseMirror first; Lexical if the proof exposes unacceptable problems | Mobile selection, IME, dictation, undo, long documents, schema extensibility, licenses/costs |
| Content | Versioned structured document JSON, stable document/block identifiers | Round-trip supported formatting and migrate old schema fixtures |
| Server | One application with clear domain modules | Keep auth, persistence, rendering, and background work separable without microservices |
| Database | Managed PostgreSQL | Provider, connection model, migrations, backups, restore procedure, region and costs |
| Local recovery | IndexedDB-backed draft persistence and pending-save queue | Storage denial/quota failures, reload, private browsing, logout and account switching |
| Authentication | Managed authentication | Provider, email delivery, session expiry, callback security, ownership checks |
| Background work | Durable jobs for scheduling and retention | Retry-safe execution, failures, cancellation, UTC/time-zone behavior |
| Discovery | Database-backed search and explicit genre/fandom filters initially | Index only published permitted material; evaluate actual search quality before another service |

Do not select dependencies solely from this table. Verify current official documentation and licenses, then write the actual decision and tradeoffs in `docs/adr/`.

## Domain and storage boundaries

Use the following conceptual entities to guide a schema, not as a final migration:

- **Account / Profile:** private account identity separate from public biography and username.
- **Document:** an owner's editable story/chapter with schema version, current server revision, and deletion state.
- **Document revision:** recoverable content snapshot with creation time and revision identity. Undo history is not a substitute for durable revisions.
- **Note / Cutting:** private writing material with source references for native movement and restoration. Reuse across separate drafts remains a policy decision.
- **Series / Chapter membership:** public ordering and metadata separate from document editing and draft state. One essay must not require a series.
- **Publication revision:** an immutable, explicitly published snapshot. Editing the manuscript must not change the public page until republished.
- **Comment:** relates to a publication and its revision. Begin with end-of-story comments; defer paragraph anchors.
- **Follow / Bookmark / Reading position:** reader-owned relationships with clear permissions.
- **Report / Block:** product enforcement state, independent of whether a staff portal exists.
- **Scheduled publication / Job:** refers to a specific approved revision, not whatever draft happens to exist when the job runs.

Public rendering must validate and sanitize supported document nodes, marks, links, and metadata. Private drafts must never leak through public caches, previews, search, sitemaps, or error logs. Readable stable URLs, metadata, and accessibility belong to the publishing layer.

## Saving and conflict protocol

Implement and test this before recruiting writers:

1. Persist edits locally with document/account identity. Show local-save success only after storage succeeds; handle storage failure visibly.
2. Send authenticated saves with a base server revision and a unique operation identifier. Validate ownership and document schema on the server.
3. Commit content and revision advancement atomically. Retried requests must not create duplicate edits or rewind content.
4. Display “Synced” only when the server acknowledges the latest relevant revision; an older response must not mark newer pending work synced.
5. Reject stale saves rather than overwriting newer revisions. Preserve the local conflict copy and offer comparison/recovery. A one-session editing lease can reduce conflicts but does not replace revision checks, especially offline.
6. Restore an old version by creating a new current version, preserving later work in history.
7. Keep pending work through session expiry and reconnect. Reauthenticate without discarding it. Isolate accounts on shared devices and define logout cleanup.
8. Tombstone deletion so an old offline client cannot silently resurrect deleted work. Define explicit recovery or a new private copy when appropriate.

Initial offline promise: continue an already-open draft through a temporary connection loss. Do not promise indefinite offline safety or fresh offline startup until tested. Local storage can fail or disappear; it is not a server backup.

## Editor and authorship boundary

Use editor transactions for native moves, cuttings, find/replace, and undo. Preserve selection and formatting, and group each action into understandable undo steps. Block clipboard import/export in the editor without disabling selection, keyboard navigation, IME, or dictation. Handle keyboard, context-menu, mobile paste, and external drop paths deliberately; prevent cut from destructively deleting text while outbound clipboard writes are blocked.

An export command is intentionally separate from clipboard operations. Decide the first export format during the proof; verify paragraphs, italics, quotes, lists, links, and intentional line breaks. Export an identified revision and make pending local content behavior explicit.

Client events and origin labels are untrusted evidence. Server validation can enforce ownership and valid edits, but cannot prove that submitted prose was human-composed or distinguish all third-party keyboard behaviors. Do not add keylogging, typing-speed scores, or AI detectors as implied requirements. No AI provider integration is needed.

## Retention and operations

Working interpretation: deleted drafts are recoverable for 30 days; active manuscripts do not expire. Before real-user storage, define revision-history coverage, account deletion, backup expiry, report records, and local copies. Do not promise a purge date unsupported by backup behavior.

Deletion jobs must be retry-safe. Restoring a backup must reapply deletion state so removed manuscripts do not reappear publicly. Test database restoration, not just backup creation. Owner backend credentials stay server-side; user credentials must not grant database-wide access. Log failures and access metadata without manuscript bodies or auth secrets. No staff portal is needed to establish these boundaries.

## Delivery milestones

### 0. Foundation decisions and setup

Inspect the repository and Figma; choose the minimal runtime/framework/editor candidate; record dependency and hosting assumptions. Create reproducible install/dev/check commands and environment-variable documentation. Establish formatting, type checking, focused tests, and private local preview. Pin dependencies and commit a lockfile.

Exit: a fresh checkout starts using documented commands, renders the visual shell, and has a written editor evaluation plan. No paid infrastructure or public deployment is needed for this gate.

### 1. Functional writing-desk proof

Implement the original desk plus notes/cuttings layout, blank state, focus/preferences, and mobile writing. Support paragraphs, deliberate line breaks, headings, bold/italic, links, quotes, lists, word count, undo/redo, native passage movement, simple cuttings, find/replace, local recovery, and manuscript export. Keep unsupported controls hidden or clearly unavailable rather than pretending they work.

Exit: core writing/revision tasks work with keyboard, touch, IME, and dictation on declared reference devices. Reload recovers a locally persisted draft. Formatting round-trips through export. Local-only builds must never claim account sync.

### 2. Durable private writer alpha

Add accounts, server ownership, revision-checked autosave, conflict preservation, history restoration, deleted-draft recovery, and trustworthy save states. Add private draft organization, notes, and basic chapters. Implement bounded retention once its detailed scope is settled. Test backup restoration and authorization before storing real manuscripts.

Exit: network loss, expired sessions, concurrent tabs/devices, storage failure, retries, and restoration do not silently lose or expose work. A small group can use the editor over several days. Fix observed reasons they leave for another editor before expanding scope.

### 3. Publishing and reader alpha

Add explicit publication snapshots, preview/review, public stories and profiles, draft-versus-live revisions, discovery/search, fanfiction metadata, save/follow, and end-of-story comments. Add basic report/block enforcement and owner backend procedures alongside comments; do not postpone all moderation until after public interaction ships.

Exit: unauthorized publication/access is prevented, private edits stay private, revisions preserve comment context, blocked relationships are enforced server-side, and only published appropriate content enters public search/caches. Author download remains available.

### 4. Serial writing and public-launch readiness

Add series navigation, chapter ordering/status, scheduling, notifications, reading position, and remaining necessary edge states. Validate age policy, launch countries, privacy disclosures, retention/backups, content policy, abuse limits, email delivery, observability, and recovery operations. Finalize age rules before public account signup; 18+ remains a proposal.

Exit: scheduled releases are retry-safe and cancellable; publication never selects an unintended later draft. Complete real-device/accessibility and recovery testing. Public launch is a separate deliberate step.

### Deferred

Generative features are excluded, not deferred. Later optional work includes images/video, coauthoring, inline comments, advanced worldbuilding, native apps, recommendation algorithms, payment systems, and a staff portal. Do not implement them to satisfy nonfunctional Figma controls.

## Acceptance and verification

Automate the failure-prone boundaries and manually test input behavior that automation cannot represent faithfully:

- Write prose, dialogue, poetry, and long documents; selection, cursor, formatting, and deliberate line breaks remain correct.
- Move and restore a passage, undo and redo, and replace text without losing words or formatting.
- Drop connection, reload, expire authentication, reorder save responses, and retry requests; save labels remain truthful.
- Edit two stale copies; both survive conflict resolution. Restore yesterday's version without destroying today's.
- Deny local storage or exhaust quota; surface the problem without falsely claiming durability.
- Test separate accounts and guessed document IDs against all draft, history, export, restore, and publication operations.
- Verify deletion boundaries and expired recovery with a controllable clock; avoid waiting 30 days in tests.
- Validate schema migration fixtures and export/import into an external reader. Import back into our editor is not an approved feature.
- Use 10,000-word chapter and 100,000-word multi-document project fixtures to measure performance on declared devices. These are test targets, not advertised capacities.
- Compare implemented screens with Figma at desktop/mobile sizes; test contrast, keyboard focus, screen-reader names, touch selection, IME composition, and dictated punctuation.
- Observe real writers completing their own work. Track errors and attempted workflows, not private prose. The research document proposes a small formative study, not a statistically representative survey.

## Remaining decisions and when needed

| Decision | Needed by |
| --- | --- |
| Runtime/framework, editor engine, extension licensing, initial export format | Milestones 0–1 |
| Exact native-creation boundary for titles, summaries, private notes, and cross-draft reuse | Before implementing those edit paths |
| Auth/database providers, server revision protocol, revision and backup retention | Milestone 2 |
| Publishing metadata, report/block enforcement details, discovery defaults | Milestone 3 |
| Exact minimum age, launch countries, public policies, hosting/service budgets | Before public launch; earlier if they affect selected vendors or alpha participants |

Do not convert the table into a long permission questionnaire. Resolve routine engineering choices with documented reasoning; ask the owner only for material product/budget decisions that cannot be inferred.
