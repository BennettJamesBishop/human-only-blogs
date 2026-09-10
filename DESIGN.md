# Human Only — Design direction

## Direction

An independent literary journal with a welcoming writing desk. This is an initial design proposal, not an approved final brand. The working name is inferred from the repository. Warmth comes from typography, a humane pace, readable prose, personal notes, and thoughtful spacing.

## Typography

- Lora: editorial titles and story text; italics for decks and quotations.
- DM Sans: navigation, metadata, controls, and explanations.
- Caveat: brief personal notes only; never essential controls or long body text.

Desktop headline: 62px. Reading title: 54px. Article body: 21px in an 800px column. Mobile headline: 39px. Controls: 15px with roughly 46px button height.

## Palette

| Token | Value | Purpose |
| --- | --- | --- |
| paper | #F8F5EE | Page background |
| sheet | #FFFCF6 | Writing surface |
| ink | #322C30 | Primary text |
| muted | #71666B | Secondary text |
| plum | #633E55 | Brand and primary actions |
| plumHover | #4C2B3F | Primary hover |
| rose | #EBDAD9 | Gentle notices and invitations |
| sage | #E2E8DE | Recommendations and process details |
| green | #45614D | Process-label text |
| line | #DCD3CD | Fine dividers |
| ochre | #E6D5A7 | Reserved accent |

## Composition

Discovery uses a broad masthead, genre navigation, one featured essay, adjacent fiction recommendations, and recent stories. The typographic jacket needs no external image upload. Reading removes surrounding feed density. The writing desk separates draft navigation, document, and compact contextual guidance. Mobile discovery stacks the same content rather than scaling the desktop layout down.

## Interaction intent

- Explain native writing and clipboard restrictions before the user invests effort.
- Block copy/paste inside the editor; do not block clipboard use across unrelated UI fields without a separate decision.
- Keep editing, saving, and publishing separate. The mockup shows a saved state and a private draft, not a working persistence implementation.
- A blocked clipboard operation should preserve the draft and show a calm notice.
- Publishing review presents category, tags, content notes, and an authorship attestation.
- “Written here” describes creation in the embedded editor, not guaranteed human authorship.
- Figma primary buttons have default, hover, focus, and disabled visual states. The initial prototype wires the main desktop journey only.

## Implementation decisions and handoff

See [PRODUCT.md](PRODUCT.md) for the latest decisions, [the engineering plan](docs/ENGINEERING_PLAN.md) for sequencing, and [Figma MCP targets](docs/FIGMA_HANDOFF.md) for implementation references.

No generative features are permitted. Dictation and ordinary spelling correction are allowed; manuscript export is approved. Biographies/comments permit normal clipboard use, while stories/chapters retain the ban. Text launches first; images/video come later. The owner uses backend access rather than a dedicated staff portal. Thirty-day retention needs precise history/backup semantics; an exact minimum age and launch countries remain undecided.

Implementation still needs to resolve title/summary/private-note boundaries, schema and input handling, evidence collection, report/block policy enforcement, providers, hosting, and account architecture. Figma includes fanfiction metadata fields, but no working taxonomy or filtering backend.

## Validation

The second edition adds 37 screens, dialogs, and state boards. See [coverage and prototype limits](docs/figma-second-edition.md). The clipboard ban remains; native passage moves, cuttings, history, and recovery support revision. Personal typography and a night focus view support reading and writing comfort. Additional screens cover fanfiction metadata, series settings, reader reporting/blocking, and empty/error states.

Inspected Figma screenshots of desktop discovery, reading, writing, mobile discovery, publishing review, and shared buttons. Checked the authored font families and the main prototype destinations. This is visual and structural review, not browser, editor, or accessibility implementation testing.
