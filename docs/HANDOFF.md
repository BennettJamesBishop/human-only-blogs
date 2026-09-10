# Fresh-agent handoff

Updated: September 10, 2026.

## Current state

The owner is moving from Codex to Conductor. This repository is the durable memory; no previous chat, local skill installation, or tool session is required to understand it.

- Repository: https://github.com/BennettJamesBishop/human-only-blogs
- Original checkout: `/Users/bennettbishop/Documents/ChatGPT/Human Only Blogs`. Use your actual checkout path in a new environment.
- Product and writer research are documented. The owner liked the Figma direction and approved the editor priorities.
- Figma contains a first edition with discovery, reading, writing, publishing review, and mobile discovery; a second edition adds 37 screens/dialogs/state boards and an index.
- No application code, package manifest, editor implementation, database, authentication, deployment, or automated application tests exists at handoff time.
- No hosting vendor, framework, exact dependency versions, authentication vendor, or database service has been selected.
- The current task produced an engineering plan and memory documents; it did not start implementation.

## Read in this order

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Portable instructions and product constraints |
| `PRODUCT.md` | Confirmed decisions and explicitly unresolved points |
| `docs/ENGINEERING_PLAN.md` | Proposed architecture and incremental build plan |
| `docs/FIGMA_HANDOFF.md` | Exact MCP file/node targets and visual workflow |
| `DESIGN.md` | Typography, palette, composition |
| `docs/writer-platform-research.md` | Evidence, prior recommendations, editor acceptance tasks |
| `docs/figma-map.json` | Machine-readable Figma inventory |
| `docs/figma-second-edition.md` | Human-readable screen inventory and prototype limits |

## Next task

Begin milestone 0 of the engineering plan, then milestone 1: verify the editor foundation and build a narrow writing-desk proof. The first objective is dependable writing, revision, local recovery, and accurate save states. Do not build every Figma screen or interpret mockup buttons as implemented features.

Before editing: inspect Git status, read these documents, verify Figma access, inspect the relevant frames, and identify available runtime tools. Select and record a minimal stack using current official documentation. Check extension licensing before committing to an editor. Do not buy services or publish a public site merely to run the proof.

Start with Figma `2:15` (original writing desk), `18:20` (notes/cuttings workspace), `18:18` (blank draft), `18:34` (mobile writing), and `18:32` (save/recovery reference). The index is a navigation aid, not a page to implement.

## Decision traps to avoid

- The user explicitly corrected an earlier transcription/misunderstanding: **nothing generative is allowed**. Do not introduce an AI rewrite feature.
- Device dictation and ordinary spelling correction are allowed. We recommended relying on existing device/browser aids; no custom dictation service has been approved or selected.
- Export is explicitly approved; the clipboard ban is still in place.
- Normal clipboard behavior for biographies/comments is separate from native story composition. Title/summary/private-note boundaries still need precision if implementation depends on them.
- Age restriction is acceptable; a specific 18+ threshold remains a proposal. There is no completed compliance review.
- The 30-day retention decision needs a precise definition for draft deletion, history, and backups. Our stated working interpretation is 30-day deleted-draft recovery, with active manuscripts retained.
- Backend access for the owner is sufficient. The user does not want a staff portal built now.
- The desire that writers never need another app is a product ambition. It does not authorize building every writing tool before testing the core editor.

## Known design limitations

Figma uses illustrative AI-generated names/prose and fictional activity. Those are design fixtures, not production content or evidence of authorship. Forms, saves, scheduling, reports, blocking, and text entry are visual concepts. Report/block policy copy is proposed behavior. Some links return to representative sample screens, not matching persisted state. Cross-page links use Figma design URLs.

The shared button component and palette are available. Many surrounding controls are auto-layout frames and text, not a fully implemented component library. Accessibility, focus management, responsive reflow, and real input behavior still require implementation and testing.

## Useful history

- `14ffd5a`: first Figma design and direction.
- `aa234eb`: writer-platform research.
- `6516d09`: approved editor priorities and clipboard ban.
- `3af1500`: second-edition screen inventory.
- `f024574`: fanfiction metadata, reader controls, and edge states.
- `3b4bcba`: corrected no-generative policy, export, owner access, retention.

The planning/handoff commit follows these commits; use `git log` for its hash.

## Suggested prompt in Conductor

> Read AGENTS.md, docs/HANDOFF.md, PRODUCT.md, docs/ENGINEERING_PLAN.md, and docs/FIGMA_HANDOFF.md. Continue with milestones 0 and 1: choose and document a minimal stack, inspect the specified Figma writing screens through MCP, and build a narrow functional editor proof. Preserve the no-generative rule, the editor clipboard ban, and manuscript export. Prioritize input correctness, native revision, and recovery. Keep proposals separate from approved decisions, and update the handoff with actual setup commands, tests, and remaining work. Do not build the entire screen inventory or deploy publicly yet.

## Updating this memory

After work, replace stale status with what actually exists. Add exact install/dev/test commands, required environment-variable names (never values), migration instructions, verified test results, next task, and new decision records. Keep this file short enough to read at the start of every fresh session.
