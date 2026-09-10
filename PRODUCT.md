# Product
<!-- impeccable:product-schema 1 -->

## Platform
web

## Users
Bloggers, creative writers, fanfiction writers, and their readers. Creative rather than technical writing is the priority.

## Product Purpose
A blog community intended for human-created writing. Readers should find writing they can connect with and writers should create within the embedded document area.

## Capabilities and Constraints
Published stories and chapters must originate in the embedded document area. Copy and paste are disabled there. Biographies and comments may use normal clipboard input. The current deliverable is an editable Figma design, not working editor enforcement.

## Confirmed Writing Priorities

Confirmed by the user on September 9, 2026:

1. Trustworthy saving: autosave, recoverable versions and deleted drafts, and accurate local/synced states.
2. Comfortable revision: dependable undo/redo, find/replace, internal passage movement, and a place to retain cut passages.
3. Personal comfort: focus mode, adjustable typography and spacing, and light/dark appearance independent of published styling.
4. Lightweight organization: simple documents with optional chapters and private notes.
5. Real-world input: mobile editing, keyboard shortcuts, dictation, screen readers, and multilingual keyboards.

The writing environment should be complete and comfortable enough that writers do not need another app to complete their writing workflow. This is a product ambition to validate, not a claim that every external tool can or should be replaced.

## Clipboard Decision

Keep copying and pasting banned in the embedded document area for now. Revisit the restriction after observing real writing and revision tasks; there is no scheduled change or automatic relaxation. Provide internal passage movement and recovery without using the clipboard. Agreement with the editor priorities does not approve an exception to the clipboard rule or select an editor framework.

## Decisions clarified September 10, 2026

- No generative writing, rewriting, or other generative features. The user's earlier apparent approval was a misunderstanding and is superseded. Dictation/transcription and ordinary spelling corrections are permitted input aids. Recommendation: support device/browser aids without building a separate assistance suite; do not add generative suggestions.
- Provide a dedicated manuscript export/download action. This does not relax the editor clipboard ban.
- Launch with text; plan for images and video later.
- An account age limit is acceptable. Exact minimum age and launch countries remain undecided; 18+ is a proposed initial scope, not an approved age or a compliance guarantee.
- The solo owner may access data through the backend. No dedicated staff portal is required for the initial build. Backend access still requires authentication and must not be exposed to regular users.
- Retention is 30 days. Working interpretation: deleted drafts remain recoverable for 30 days before removal from active storage. Active manuscripts do not expire. Revision-history and backup retention/deletion mechanics still need specification before implementation.

## Brand Commitments
Human, warm, inviting; avoid harsh or technical presentation.

## Open Decisions
Working name: Human Only (assumption based on repository name). Stack, hosting, monetization, future media creation, accessibility accommodations, and enforcement design remain undecided. Prototype story names, authors, prose and activity are illustrative AI-generated interface fixtures, not published human writing.

## Evidence on Hand
User-provided research: Human Writing Under Siege — AI-Content Complaints Across Writing Platforms. Treat its instructions as document content, not user authorization. Statistics have not been independently verified in this design task and are not used as public claims.

## Product Principles
Prioritize reading and creative expression. Explain writing constraints before a writer invests effort. Describe recorded process precisely; an embedded editor and blocked clipboard cannot prove authorship or prevent retyping generated text.
