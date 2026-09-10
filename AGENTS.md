# Project instructions

This repository is Human Only Blogs, a warm literary publishing platform with a compulsory embedded writing environment. The owner is a solo developer. These instructions are portable across agent tools.

## Start here

1. Read `docs/HANDOFF.md` for current state and the next task.
2. Read `PRODUCT.md` for confirmed product rules.
3. Read `docs/ENGINEERING_PLAN.md` for the proposed architecture, milestones, and release gates.
4. For UI work, read `DESIGN.md` and `docs/FIGMA_HANDOFF.md`; use `docs/figma-map.json` for exact node IDs.

New user instructions take precedence. Product decisions take precedence over older research recommendations and illustrative Figma copy. Keep proposals distinguishable from approved decisions.

## Non-negotiable product context

- No generative writing, rewriting, suggestions, or other generative product features. Earlier apparent approval was explicitly corrected. Ordinary spelling correction and dictation/transcription are allowed; never silently replace them with a generative service.
- Stories and chapters must be composed in the embedded editor. Keep copy/paste banned there. Biographies and comments may use normal clipboard input. Dedicated manuscript export is approved.
- Support revision through native passage moves, cuttings, undo/redo, and recovery. Do not implement the restriction as a global keyboard blockade that breaks normal input or unrelated fields.
- Text-only launch. Images and videos are future work.
- Save states must distinguish local persistence from server acknowledgement. Never silently overwrite a conflicting draft.
- No dedicated staff portal in the initial scope; the owner can use authenticated backend access.
- Thirty-day retention is approved, but its precise coverage is not fully settled. See PRODUCT.md. Do not expire active manuscripts.
- An age limit is acceptable; 18+ was recommended, not explicitly selected. Launch countries remain open.
- Embedded creation and clipboard restrictions cannot prove human authorship. Do not market AI detection or guaranteed human provenance.

## Working practice

- Preserve the approved warm Figma direction; do not redesign into a technical dashboard.
- Start with a functional writing desk and recovery, not all Figma screens at once.
- This repository began as documentation only. Do not claim tests, services, database migrations, or deployments exist until they do.
- Choose ordinary implementation details autonomously within scope; flag material product ambiguities at the point they affect implementation. Do not reopen settled decisions.
- Before choosing dependencies, verify current official documentation, licensing, and costs. Editor/framework/provider recommendations in the plan are not installed dependencies.
- Keep credentials and real manuscripts out of Git, fixtures, logs, and analytics. Private drafts must not enter public rendering, caches, feeds, or search.
- Use meaningful persistence, authorization, input, and publishing tests; screenshots alone cannot validate an editor.
- After each milestone, update the status, commands, remaining work, and decisions in `docs/HANDOFF.md`. Record lasting architecture choices in `docs/adr/` when made. Do not mark proposals accepted without evidence.
- Preserve unrelated changes. Use `codex/` for a new branch unless the user specifies otherwise; inspect the current checkout before changing Git state.

## Figma

File key: `8nSFeWDJXfxPl1ZB1KRrrC`. Start implementation with writing desk `2:15` and notes/cuttings `18:20`, not index frame `26:103`. See `docs/FIGMA_HANDOFF.md` for MCP calls, visual references, limitations, and connection requirements.
