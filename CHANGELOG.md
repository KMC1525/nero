# Changelog

All notable changes to NERO are recorded here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the version is the **suite version** shown in each prompt's header.

## [1.2] - 2026-11-03

### Added

- **`nero-jps`: text-only mode.** An image is no longer required. The appearance is built from the user's written description: every detail the user gave is kept and the gaps are filled with specific, consistent detail. JPS never asks for an image.
- **`nero-jps`: fully multimodal input**, like the rest of the suite. It now accepts several images at once, audio (voice, pace, accent, and mood become speech rules), video, documents, and **existing character cards or lorebooks** to convert to the five-section format, in any combination, with a source-priority rule (user prompt, then images, then other media).
- **`nero-jps`: optional multimodal add-ons**, delivered only on request and after the unchanged card: `### Visual Prompt`, `### Voice Direction`, `### Ambience`, and `### Alternate Greetings`. JPS can also generate images or audio directly where the platform supports it. The Character Card V2 JSON export is now documented together with them (section 10).

### Changed

- `nero-jps` source rules (section 6) now cover every source type: a minor or childlike figure in an image **or in text** gets no sexual or romantic content; video, voice recordings, documents, and text prompts about a **real person** yield a SFW, non-sexual character only; real people are never identified from their face or voice. Original and fictional characters in text-only mode get the full range of the active content mode.
- The output contract no longer asks for an image: the only reason to ask for input is when the user sends nothing usable.
- `README.md` and `README.pt-BR.md` updated: new JPS inputs table, optional add-ons, text-only example, updated source rules, mermaid label, and version table.
- The `nero-jps` row in the *NERO suite* table of every agent now reads "from any source or plain text". Core Directives remain identical in all 14 files.
- The `Version` field in every prompt header moved from `1.1` to `1.2`.
- `nero-character` hand-off to `nero-jps` now mentions other media and plain text.

## [1.1] - 2026-11-03

### Added

- **`nero-jps`** (`characters/nero-jps.md`): a new agent that turns an **image plus a user prompt** into a ready-to-paste **character card** for **JanitorAI, Front Porch AI, SillyTavern, and derivatives** (KoboldCPP, Oobabooga, and other frontends that use the common character-card fields).
  - Output is exactly five sections, with fixed English headings: **Description, Personality, Scenario, First Message, Example Dialogue**, in 2,000 to 3,000 tokens with a per-section budget.
  - Detailed visual analysis of the image (body type, apparent age, skin tone, hair, face, clothing, pose, context), with estimated height and weight, and no traits that contradict the image.
  - Platform profiles for `sillytavern` (default), `janitor`, and `frontporch`, plus `{{char}}` / `{{user}}` macros and `<START>` example-dialogue blocks.
  - Optional **Character Card V2 JSON** export.
  - Plain-language settings: platform, content mode (`SFW` / `NSFW` / `Auto`), output language, narration style, export.
  - Strict output contract: the card and nothing else.
- `CHANGELOG.md`.
- `README.pt-BR.md`: the previous Portuguese README, kept and updated.

### Changed

- `README.md` is now in **English** and was rewritten for 14 agents: new JPS section with a section-to-field mapping per platform, updated structure tree, workflow diagram, contributing notes, and a versioning section. The Portuguese version moved to `README.pt-BR.md`.
- The *NERO suite* table inside the Core Directives of **all agents** now lists `nero-jps`. The Core Directives remain identical in every file.
- The `Version` field in every prompt header moved from `1.0` to `1.1`.
- `nero-character` now hands off platform-ready cards built from an image to `nero-jps`.

### Safety

- JPS applies the suite's hard limits to images: the character must be an explicit adult; an image of a minor or childlike figure gets no sexual or romantic content; a **photograph of a real person** yields a SFW, non-sexual character only; real people are never identified from their faces.

## [1.0] - 2026-11-03

### Added

- First release: **13 system prompts** in four categories, all in English and Markdown, each supporting SFW and NSFW content, multimodal input and output, and any language.
  - `characters/`: `nero-character`, `nero-multi-character`
  - `worldbuilding/`: `nero-worldbuilding`, `nero-places`, `nero-rooms`, `nero-building`, `nero-economy`
  - `adventure/`: `nero-adventure`, `nero-combat`, `nero-narrative`
  - `items/`: `nero-items`, `nero-equipments`, `nero-weapons`
- A shared Core Directives block kept identical across agents, with three hard limits (no sexual content involving minors, none about real people, no real-world operational instructions).
- Project `README.md` in Portuguese.

[1.2]: https://github.com/KMC1525/nero/releases/tag/v1.2
[1.1]: https://github.com/KMC1525/nero/releases/tag/v1.1
[1.0]: https://github.com/KMC1525/nero/commit/76056bac08a9b40875bd651f1afe80284abe940a
