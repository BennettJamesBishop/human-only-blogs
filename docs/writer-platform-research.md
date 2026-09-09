# What writers value — publishing platforms and embedded writing

Research date: September 9, 2026. Prepared for Human Only Blogs.

## Recommendation

Build a writing environment that earns a writer's trust before relying on the human-only proposition to attract them. Our requirement to compose on-platform makes editor quality unusually consequential: writers cannot simply draft in their preferred app and paste the finished piece into our publishing form.

The strongest direction is a calm default editor, dependable recovery, lightweight structure for longer work, and a publishing community that connects the writer with interested readers. “Rich text” is only one part of that experience.

These are research-based recommendations, not changes to the approved product constraints or Figma file. In particular, the existing copy/paste restriction remains unchanged pending a product decision.

## Evidence and limits

This is qualitative desk research, combining first-person writer discussions, a publisher's migration account, current product documentation, and a public feature-request board. It is not a representative survey, a hands-on editor benchmark, or proof that a feature causes retention. Community comments are self-selected; vendor testimonials are selected by vendors. Older discussions help identify durable workflows but cannot establish current product defects.

Search snippets were used for discovery; the central community and migration findings were checked against opened pages. Novlr's public roadmap also supplied request-level signals. AO3's posting FAQ could not be retrieved, so this report does not assert its current draft retention or autosave behavior. No prevalence estimates are inferred from votes or comment counts.

## What is worth learning from each platform

| Platform | Evidence of value | Implication for Human Only |
| --- | --- | --- |
| Google Docs | Writers describe easy access across devices and the reassurance of cloud saves. Official documentation supports recovery through version history. [Writer discussion](https://www.reddit.com/r/writers/comments/17r5e3u), [version history](https://support.google.com/docs/answer/190843?hl=en_) | Make recovery, resuming work, and clear save states part of the core experience. |
| Scrivener | Users explicitly praise split views, document organization, and split/move/merge operations. Others use only a subset of its tools. [Writer forum](https://forum.literatureandlatte.com/t/what-is-your-favourite-scrivener-feature-and-what-is-the-most-useful-feature/121556) | Offer chapters, notes, and rearrangement without forcing an elaborate workspace on an essayist. |
| Novlr | Its writing-focused interface receives praise in writer discussion. Its product offers focus mode, notes, goals, and version history; its request board surfaces demand for reading aloud, formatting control, and offline capabilities. These are different evidence types, not a satisfaction score. [Writer discussion](https://www.reddit.com/r/writers/comments/17r5e3u), [product](https://www.novlr.org/), [requests](https://roadmap.novlr.org/) | Let writers customize their workspace and reveal optional tools only when needed. |
| Substack | Publisher Myles McNutt describes recommendations as a meaningful subscription source and comments as a valuable part of his archive, even while explaining why he left. [Migration account](https://episodicmedium.substack.com/p/changing-channels-episodic-medium) | Reader relationships and writer-to-writer recommendations can matter more than a sophisticated feed. |
| Ghost | Content and member export are documented capabilities. McNutt's move illustrates the appeal of independence as well as the cost of moving a community. [Export documentation](https://ghost.org/help/exports/), [migration account](https://episodicmedium.substack.com/p/changing-channels-episodic-medium) | Make ownership and portability tangible. Keep the author's work recoverable and exportable. |
| Medium | Publications, following feeds, digests, and curation provide several distribution paths. This is a documented platform benefit, not evidence that every writer receives meaningful reach. [Distribution documentation](https://help.medium.com/hc/en-us/articles/360018677974-What-happens-to-your-story-when-you-publish-on-Medium) | Give new writers a credible route to discovery, with transparent editorial selection and topic browsing. |
| AO3 / Wattpad | Community participants praise AO3's filters and Wattpad's inline reactions, while disagreeing about added social features. [Fanfiction discussion](https://www.reddit.com/r/AO3/comments/1t6luu6/are_there_any_features_from_other_fanfiction/) | Treat precise discovery and optional reader response as separate design jobs. |
| Royal Road | Its author tools document chapters, drafts, author notes, preview, and scheduled releases. [Chapter documentation](https://www.royalroad.com/support/knowledgebase/83) | A serialized story needs a series/chapter model and release controls, not just unrelated blog posts. |

## Findings that should shape the editor

### 1. Trust in saved work comes before delight

One writer reports abandoning Notion after losing part of a paragraph. That does not establish a general defect in Notion; it illustrates how a single perceived loss can destroy trust. Other participants describe combining apps for drafting, planning, and feedback. [First-person discussion](https://www.reddit.com/r/writers/comments/1eaame3/what_are_the_writing_tools_youre_currently_using/)

Google Docs provides earlier-version restoration. Medium also exposes revision history, although its help page says that feature is not available in its mobile apps. These are separate from ordinary undo. [Google documentation](https://support.google.com/docs/answer/190843?hl=en_), [Medium documentation](https://help.medium.com/hc/en-us/articles/214895528-Revision-history)

**Recommendation:** autosave, local recovery, recoverable deletion, and version restoration belong in the first usable editor. Display distinct states: “Saving,” “Saved to this device,” “Synced,” and “Couldn't sync.” Never present a local write as proof of server backup. Recovering an earlier version should create a new version instead of silently destroying later work.

### 2. Revision means moving and trying things

Scrivener users identify splitting, moving, merging, and keeping reference material visible as important workflows. Its documentation confirms snapshots and manuscript reorganization. [Writer forum](https://forum.literatureandlatte.com/t/what-is-your-favourite-scrivener-feature-and-what-is-the-most-useful-feature/121556), [Scrivener features](https://www.literatureandlatte.com/scrivener/overview)

**Recommendation:** writers need to move a paragraph, park an unused passage, reorder a scene, compare a revision, and undo the experiment. A “Cuttings” area for text created here could preserve material without making writers maintain separate documents. This is a proposed feature, not evidence that every writer wants one.

### 3. Comfort is personal

Writer discussions contain both praise for minimal, attractive interfaces and frustration with extensive tools. The same discussion includes requests for easy navigation and reading aloud. The useful conclusion is variation in preferences, not one universal ideal editor. [Writer discussion](https://www.reddit.com/r/writers/comments/17r5e3u)

**Recommendation:** keep the warm Figma identity, but let the writer choose serif or sans-serif, text size, line spacing, and a darker theme. Separate writing preferences from the published article's typography. Add a single focus-mode action; hide sidebars and notifications without taking away save status or recovery access. Make goals and streaks optional.

### 4. A novel and an essay should not require the same setup

Scrivener documents section-based writing, outlines, and side-by-side views. Novlr's current workspace includes notes and planning tools. [Scrivener](https://www.literatureandlatte.com/scrivener/overview), [Novlr](https://www.novlr.org/)

**Recommendation:** start an essay with one document. Let a longer project grow into chapters and private notes. Notes should remain available beside the manuscript without stealing its cursor position. Separate project organization from public chapter order and release status.

### 5. Writing must survive an ordinary day

Novlr documents continued writing after an already-open app loses connectivity, local browser storage, and syncing on reconnect. It explicitly cautions against treating prolonged offline browser use as equally safe as server-synced work. [Offline documentation](https://help.novlr.org/en/article/can-i-use-novlr-offline-ctck05/)

**Recommendation:** test brief network loss, laptop sleep, reload, expired sessions, and a second device. Promise only the offline behavior actually supported. Multi-tab or multi-device conflicts must preserve both versions or merge safely; silent overwriting is unacceptable.

### 6. Human composition is broader than physical keystrokes

Google Docs supports voice typing and voice editing in supported browsers. Accessible dragging guidance also calls for alternatives to drag operations. [Google voice input](https://support.google.com/docs/answer/4492226?hl=en), [W3C dragging guidance](https://www.w3.org/WAI/WCAG22/Understanding/dragging-movements)

**Recommendation:** distinguish speech transcription from generative composition. Test dictation, screen readers, keyboard-only operation, mobile keyboards, and multilingual input methods. Do not treat typing speed, pauses, or unusual input patterns as guilt. Provide “Move before/after…” commands as well as any drag interaction.

## The clipboard decision needs deliberate testing

The current rule is a complete copy/paste block inside the document area. That creates at least four different problems: importing external text, relocating one's own words, exporting/backing up one's work, and reusing passages across drafts. They do not have the same effect on the human-only objective.

| Action | Proposed treatment | Status |
| --- | --- | --- |
| Paste external prose into publishable content | Block, with an explanation that does not alter the draft | Consistent with current rule |
| Move text already created here | Internal move command and keyboard/touch alternatives, preserving its recorded origin | Proposed way to retain the strict clipboard rule |
| Keep a deleted passage for later | Move to Cuttings; restore through an internal operation | Proposed feature |
| Copy/download one's own work for backup or submission | Permit a dedicated export; separately reconsider the outbound copy ban | Recommendation requiring a product decision |
| Reuse a passage from another native draft | Explicit internal insert with source reference, if the product permits reuse | Open policy decision |
| Paste a URL into a link dialog | Consider allowing it as metadata rather than prose | Open scope decision |
| Quote an outside work in an essay | Decide whether manual entry plus attribution is sufficient or a marked quotation path is needed | Open scope decision |
| Dictate original sentences | Support transcription, subject to a clearly defined policy | Recommended accessibility direction |
| Accept a beta reader's rewritten sentence | Decide whether multiple human contributors are allowed and how credit works | Open authorship decision |

**My recommendation:** block external text import while preserving normal manipulation and export of native work. If the full clipboard ban is essential, internal move/cuttings/restore actions must be available from the start. Do not silently relax the rule in implementation.

Native-origin records are useful evidence of actions performed in the app, not proof that the ideas or words were human-composed. Retyping outside text remains possible. Offline and assistive-input support should not be traded away for an unsupported certainty claim.

## What makes the blog platform worth publishing on

### Discovery by interest and by people

Substack documents writer-selected recommendations; Medium documents publication-based distribution. Neither mechanism guarantees an audience. [Substack recommendations](https://on.substack.com/p/recommendations), [Medium distribution](https://help.medium.com/hc/en-us/articles/360018677974-What-happens-to-your-story-when-you-publish-on-Medium)

**Recommendation:** start with genre/topic browsing, a chronological Following view, a small editorial selection, and writer-curated recommendations. Do not rank mainly by posting frequency; that would work against slow, considered writing. Show a new writer how a piece can be discovered rather than leaving them with an empty public page.

### Feedback that feels like a reader was there

Some fanfiction participants value inline comments enough to cross-post for them. Others explicitly resist making their archive more competitive or social-media-like. Requests also include persistent filters and easier reading controls. [Community discussion](https://www.reddit.com/r/AO3/comments/1t6luu6/are_there_any_features_from_other_fanfiction/)

**Recommendation:** support end-of-story comments first; test optional paragraph-anchored responses later. Keep public reactions out of private drafting mode. Distinguish public reader comments from private editorial feedback. Give authors moderation controls and readers mute/report tools. Preserve comments against a specific published revision so later edits do not attach responses to the wrong sentence.

### Continuity for serial writing

Royal Road's documented release controls include scheduled chapters, local-time display, and an optional public schedule. [Royal Road documentation](https://www.royalroad.com/support/knowledgebase/83)

**Recommendation:** support series subscriptions, chapter navigation, completed/ongoing status, and a reader's last position. Add scheduling before pursuing complex monetization. If fanfiction is in the first release, fandom, relationships, ratings, and content warnings need dedicated fields—not just a generic topic selector.

### Ownership without a trap

Ghost documents content/member export; Substack also documents export of posts and subscribers. McNutt's migration account shows that comments can be part of the valuable archive and that moving platforms can lose affordances. [Ghost exports](https://ghost.org/help/exports/), [Substack exports](https://support.substack.com/hc/en-us/articles/360037466012-How-do-I-export-my-posts), [publisher account](https://episodicmedium.substack.com/p/changing-channels-episodic-medium)

**Recommendation:** offer a useful manuscript export and explain what transfers. Subscriber export applies only to readers who actually opted into an email relationship, not private platform follows. Do not make writers feel that drafting here means surrendering access to their own work. Define pricing and any paid publishing separately; do not make them prerequisites for basic recovery.

## Priorities

| Stage | Writing environment | Publishing environment |
| --- | --- | --- |
| Editor proof, before public launch | Reliable selection/caret, paragraphs and deliberate line breaks, headings, bold/italic, links, quotes, lists, undo/redo, autosave, recovery, local unsynced state, native-text movement, find/replace, word count, keyboard/mobile/IME checks | Private preview only; keep this experiment small |
| Small writer alpha | Version history, export, writing preferences, focus mode, private notes, simple chapter organization | Author pages, tags/search, readable articles, follow/save, comments and moderation, separate draft/published revisions |
| Before actively recruiting serial writers | Reorder/split chapters, project search, reliable long-project navigation | Series subscriptions, chapter status, content warnings, scheduling, reading position |
| After evidence of repeat use | Beta-reader comments, compare revisions, read-aloud, advanced cuttings workflow | Optional inline reactions, curated collections, digest preferences, useful author analytics |
| Defer | Full Scrivener clone, elaborate worldbuilding database, collaborative coauthoring, gamified streaks | Engagement-maximizing social feed, complicated paywalls, elaborate rankings |

Priorities are our product judgment. The appropriate order of read-aloud, notes, and collaboration should be tested with actual target writers rather than assumed from online discussion.

## Selecting the editor engine

Use an established editor framework rather than inventing selection, history, and document structure on top of a raw editable element. Tiptap provides a headless ProseMirror-based editor and extensions; Lexical is an extensible editor framework with an explicit focus on reliability, accessibility, and performance. These are candidate foundations, not complete writing products. [Tiptap](https://tiptap.dev/docs), [ProseMirror guide](https://prosemirror.net/docs/guide/), [Lexical](https://lexical.dev/docs/intro)

**Provisional recommendation:** prototype the critical writing tasks in Tiptap/ProseMirror first, with Lexical as the comparison candidate. Do not select solely on a polished demo. Neither vendor documentation nor a framework's positioning establishes that our configured editor is accessible, fast, or loss-resistant. Saving, recovery, native-origin records, publishing, and permissions remain application responsibilities. Review extension costs and licensing at selection time. AI add-ons are unnecessary to this use case.

## Acceptance test for a writer-ready editor

These are proposed release tests, not tests already executed:

1. Draft an essay containing italics, dialogue, an em dash, links, a quotation, and a poem with intentional line breaks. Preview preserves meaning and spacing.
2. Move a paragraph without using the clipboard; park a passage in Cuttings; undo and restore without losing words or formatting.
3. Continue typing during a connection drop. Reconnect, reload, and compare the exact text. The save indicator tells the truth throughout.
4. Lose authentication while editing. Reauthenticate without discarding unsynced writing.
5. Edit the same draft in two tabs or devices. Confirm that the conflict is resolved without silently overwriting either version.
6. Restore yesterday's draft while keeping today's version recoverable. Recover a deleted draft.
7. Test a 10,000-word chapter and a 100,000-word project on declared reference devices. Record input delay, selection behavior, search responsiveness, and recovery time. These sizes are test fixtures, not established capacity promises.
8. Complete editing with keyboard only, a screen reader, touch selection, dictation, and an IME. Check that clipboard blocking does not break legitimate input.
9. Export a draft and reopen it in a standard document reader. Verify that paragraphs, emphasis, and intentional line breaks survive.
10. Change a published piece privately, preview it, and publish the new revision deliberately. Existing comments remain intelligible.

Run a small formative study with approximately eight writers spanning essays, serial fiction, fanfiction, and access/input needs. Ask them to bring a real task, not rate a mockup. Observe a session, then invite a week of use. Track where they try to leave for another tool, attempted clipboard actions by task, recovery failures, and whether they voluntarily return for a second writing session. This sample is for discovering problems, not estimating market adoption.

## Implications for the next Figma pass

Keep the visual direction the user liked. Add the behaviors that make it credible:

- Focus mode and personal writing preferences.
- Save status detail, offline/error states, and version restoration.
- Manuscript / Notes / Cuttings workspace, with simple mode as the default.
- Internal move actions and accessible alternatives to dragging.
- Chapter organization and a separate public release schedule.
- Private feedback and public comments as clearly different experiences.
- Export and ownership affordances.

The immediate next milestone should be a tested writing desk, not a broader collection of polished publishing screens.
