# Figma MCP handoff

## Exact file and entry points

- File: **Human Only — A home for words**
- File key: `8nSFeWDJXfxPl1ZB1KRrrC`
- [Full design](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC)
- [Screen index](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=26-103), node `26:103`
- First page: `0:1`, “First edition — Explore, read, write”
- Second page: `18:16`, “Second edition — The whole writing life”
- Team `1185331789136841131`, folder `652260310`.

The index is not a product screen. Do not implement it as a landing page. The older browser URL pointing to `2:13` is discovery; it is not the writing workspace.

## Start implementation with these frames

| Purpose | Node ID | Link |
| --- | --- | --- |
| Original writing desk / visual baseline | `2:15` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=2-15) |
| Expanded notes and cuttings workspace | `18:20` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-20) |
| First blank draft | `18:18` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-18) |
| Draft library | `18:19` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-19) |
| Night focus | `18:21` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-21) |
| Preferences | `18:30` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-30) |
| Mobile writing | `18:34` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-34) |
| Save/recovery state specimens | `18:32` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-32) |
| Save details | `25:86` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=25-86) |
| Version history | `18:22` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-22) |
| Recently deleted | `18:23` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=18-23) |
| Move passage | `25:83` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=25-83) |
| Find/replace | `25:84` | [Open](https://www.figma.com/design/8nSFeWDJXfxPl1ZB1KRrrC?node-id=25-84) |

For publication later: discovery `2:13`, reading `2:14`, publishing review `2:205`, provenance explanation `2:206`, mobile discovery `2:16`. All 37 second-edition targets are in `figma-map.json`, including fanfiction `35:119`, series settings `35:188`, reporting, blocking, and edge states.

The expanded workspace complements the original desk; it does not replace all first-edition designs. Preserve the first edition's typography and visual character while using the second edition for additional workflows.

## Connecting from a fresh agent

The Figma connection used in Codex is not stored in Git and may not transfer to Conductor. Configure an available Figma MCP integration authenticated to an account with access to this file. Discover the tools it actually exposes rather than assuming Codex-specific prefixes exist.

For implementation, use the integration's **get_design_context** and **get_screenshot** tools with the exact file key and node ID. If Figma skills are installed, read **figma-design-to-code** before `get_design_context`. Follow that tool's current schema and instructions; available capabilities may differ between integrations.

Illustrative argument targets, using tool names without host-specific prefixes:

```json
{"fileKey":"8nSFeWDJXfxPl1ZB1KRrrC","nodeId":"2:15"}
```

Then fetch `18:20`, `18:18`, and `18:34`. Inspect screenshots alongside design context. Use metadata to narrow large nodes instead of requesting the whole file. Generated code is reference material to adapt to the selected stack, not a ready-made application architecture.

If design context is unavailable, use whatever read-only metadata/screenshot tools are exposed plus the checked-in map and DESIGN.md. Report the limitation; do not claim exact visual implementation without inspecting the design. Do not create a replacement Figma file because access is missing.

For writing to Figma, the previous integration exposed **use_figma**. Read its **figma-use** guidance before using it, plus **figma-generate-design** for assembled screens and **figma-generate-library** for components. Those skills are environment tools, not repo dependencies. A Figma write-capable plugin is not required merely to implement the website from read-only design references.

## Known write-tool behavior from the previous session

These notes apply to the previous use_figma integration; check current tool documentation before relying on them:

- JavaScript uses the Figma Plugin API; return created/mutated node IDs explicitly.
- Page context resets to the first page each invocation. For second-edition work, call `await figma.setCurrentPageAsync(await figma.getNodeByIdAsync('18:16'))`; switch at most once per invocation.
- Await font loads before mutating text. Use existing node fonts when editing.
- Failed scripts were atomic: read the error and correct it before retrying.
- NAVIGATE destinations must be a different top-level frame on the same page. Existing cross-page links use design URLs, which leave the prototype flow.
- Shared button labels expose multiple TEXT properties across variants; inspect and override the relevant properties instead of assuming a single generic label key.

## Shared visual assets

- Button component set `2:292`.
- Primary variants: default `2:276`, hover `2:278`, focus `2:280`, disabled `2:282`.
- Quiet variants: default `2:284`, hover `2:286`, focus `2:288`, disabled `2:290`.
- Fonts: Lora Regular/Italic, DM Sans Regular/Medium, Caveat Regular. Caveat is a small accent, not a body/UI font.
- Text styles follow `Family/Style/Size` naming.
- Color variables: `paper`, `sheet`, `ink`, `muted`, `plum`, `rose`, `sage`, `green`, `line`, `ochre`, `plumHover`. Exact values are in DESIGN.md.
- Button control variables: `paddingX`, `paddingY`, `radius`.
- Most desktop frames are 1440px wide; mobile frames 390px; dialog specimens 640px. Heights hug content. Implement responsive behavior, not fixed-height screenshots.

## What screenshots do not establish

The file is an editable visual proposal. Controls are not proof of working authentication, saving, text editing, reports, scheduling, or state changes. Save/recovery is a specimen board, not one screen displaying every state at once. Dialogs are shown as standalone frames; implement appropriate dialog semantics, focus restoration, and mobile layouts.

Export was approved after the main design pass and has no dedicated export frame in the map. Add an accessible export affordance consistent with the desk when implementing; do not omit the feature because it lacks a mockup.

Age rules, 30-day deletion wording, owner backend access, and the precise non-generative input policy were clarified after design. PRODUCT.md wins over older Figma copy. The prototype contains no real user data and uses illustrative AI-generated writing. Do not seed public production content from it.

Inspect actual screenshots for visual fidelity and test actual browser behavior for usability. Previous bounds/font checks passed but were not functional or accessibility certification.
