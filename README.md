# Human Only Blogs

A warm, literary home for bloggers, creative writers, fanfiction writers, and readers. Published writing must originate in an embedded document editor with copy and paste disabled.

## Continue development with a fresh agent

Start with [AGENTS.md](AGENTS.md) and [the handoff](docs/HANDOFF.md). The [engineering plan](docs/ENGINEERING_PLAN.md) defines the next milestones, and the [Figma MCP handoff](docs/FIGMA_HANDOFF.md) identifies exact implementation frames. `CLAUDE.md` points Claude-based tools to the same project memory.

The next milestone is a functional writing-desk proof. The repository currently contains design and planning documentation only; no application setup commands exist yet.

## Design

[Open the Figma design](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=2-13)

Created with Figma MCP in the requested team folder. Working name: **Human Only**.

The first edition includes:

- Desktop discovery and reading screens.
- An embedded writing desk with a blocked-clipboard notice.
- Publishing review and an explanation of the “Written here” label.
- Mobile discovery at 390px.
- Shared button components with default, hover, focus, and disabled variants; color variables and text styles.

The main desktop prototype links discovery → reading → writing → publishing review. The label opens its explanation. Secondary controls and mobile navigation are visual concepts rather than complete interactions.

## Status

The [second edition](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=26-103) adds 37 screens and dialogs for drafting, revision, recovery, series, reader libraries, profiles, preferences, mobile use, fanfiction metadata, reporting, blocking, and empty/error states. See the [complete inventory](docs/figma-second-edition.md).

Design stage. No website, backend, editor enforcement, autosave, or publishing system is implemented. Story titles, authors, prose, and save states are illustrative AI-generated mockup fixtures; they are not published human-authored content.

See [PRODUCT.md](PRODUCT.md) for the brief, [DESIGN.md](DESIGN.md) for visual decisions, and [docs/figma-map.json](docs/figma-map.json) for editable frame references.

[Writer-platform research](docs/writer-platform-research.md) covers what writers value, the embedded editor's priorities, the clipboard tradeoff, and proposed acceptance tests.

## Authorship model

Blocking clipboard imports creates friction; it does not prove human authorship. The design describes where writing was created rather than promising perfect AI detection. Accessibility, privacy, media creation, and enforcement require further product decisions before implementation.
