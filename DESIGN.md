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

## Decisions before implementation

1. Support for dictation, IME composition, assistive input, and accessibility accommodations.
2. Moving passages without copying/pasting; undo/redo; recovery and export of the writer's own drafts.
3. Whether title, summary, comments, and author biography also require native creation.
4. How in-product cover art or other non-text media would be created under the all-content rule.
5. Evidence collection, consent, retention, reader visibility, moderation, and appeals.
6. Fanfiction-specific metadata: fandom, rating, relationships, chapter status, and content warnings.
7. Stack, hosting, account model, and monetization remain open.

## Validation

The second edition adds 28 screens, dialogs, and state boards. See [coverage and prototype limits](docs/figma-second-edition.md). The clipboard ban remains; native passage moves, cuttings, history, and recovery support revision. Personal typography and a night focus view support reading and writing comfort.

Inspected Figma screenshots of desktop discovery, reading, writing, mobile discovery, publishing review, and shared buttons. Checked the authored font families and the main prototype destinations. This is visual and structural review, not browser, editor, or accessibility implementation testing.
