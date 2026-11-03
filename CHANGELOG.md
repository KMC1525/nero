# Changelog

All notable changes to NERO are recorded here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the version is the **suite version** shown in each prompt's header.

## [1.5] - 2026-11-03

### Added

Five practical, tool-integration agents, all in `tools/`, each following the suite pattern (Core Directives, Quick/Standard/Deep depths, Compact Block, multimodal input and output, SFW/NSFW/Auto modes, removable adult modules, and hand-offs). The suite grows from 24 to **29 agents**.

- **`nero-st`** (`tools/nero-st.md`): SillyTavern and derivatives. World Info / Lorebook engineering (keys, regex keys, secondary-key logic, constant, order, position, depth, probability, recursion switches, sticky/cooldown/delay, inclusion groups, global budget), Regex Scripts (find, replace, placement, depth, display versus prompt, test strings), Quick Replies and STscript starters, Author's Note, Character Card V2/V3 fields, generation presets, instruct and context templates, group chats, and context-management strategy. Marks every option as version-dependent and states that presets carry style and roleplay rules, not safety-evasion instructions.
- **`nero-card`** (`tools/nero-card.md`): conversion and optimization of character cards across SillyTavern, JanitorAI, Front Porch AI, Agnai, RisuAI, and derivatives. Modes: convert, optimize, merge, audit, upgrade/downgrade (V2 and V3), and split. Includes a cross-platform field map, per-field token budgets in three tiers, platform best practices, V2/V3 JSON, a severity-ranked lint checklist, and a card package with a conversion note.
- **`nero-comfy`** (`tools/nero-comfy.md`): ComfyUI and Stable Diffusion-family pipelines. Prompt packages by model family, a reusable **Character Lock**, workflow structure as a node chain with a Mermaid diagram (LoRA stack by role and strength, ControlNet, IP-Adapter, regional prompting, upscale, detailer, inpainting), a consistency plan, variation and sprite batches, and optional best-effort workflow JSON. Built-in safety rules for image work (see Safety).
- **`nero-context`** (`tools/nero-context.md`): context compression and prioritization. Invariants, priority tiers P0 to P3, budgets for 4k, 8k, 16k, and 32k+ windows, compression techniques, density levels, a rolling-summary template, a Loss Report, and a consistency check. Keeps adult material intact and separable.
- **`nero-renpy`** (`tools/nero-renpy.md`): adaptation to Ren'Py visual novels. Project map and Mermaid route map, character definitions, `default` variables and flags, a script-conversion guide (labels, menus, jump/call/return, transitions, text escapes), requirements tables for endings, an asset manifest that hands art prompts to `nero-comfy`, an age-gated mature-content pattern with SFW fallbacks, and a test list including Ren'Py Lint.

### Changed

- The *NERO suite* table inside the Core Directives of **every agent** now lists the five new agents. Core Directives remain identical in all 29 files.
- The `Version` field in every prompt header moved from `1.4` to `1.5`.
- Hand-offs: each new agent hands off to `nero-jps`, `nero-character`, `nero-lorebook`, `nero-narrative`, `nero-scenario`, `nero-romance`, and `nero-worldbuilding`, and to the other new tool agents where relevant. `nero-lorebook`, `nero-jps`, `nero-character`, `nero-scenario`, `nero-romance`, `nero-narrative`, `nero-worldbuilding`, and `nero-multi-character` now point to the relevant new agents.
- `README.md` and `README.pt-BR.md` updated: agent count (24 to 29), repository tree, agent tables, workflow diagram, and version table.

### Safety

- `nero-comfy` requires every subject of an NSFW or suggestive image prompt to be an explicit adult, adds child-related terms to negative prompts, and refuses suggestive prompts for minors or childlike figures. It does not build prompts, LoRAs, face references, IP-Adapter or face-swap steps to depict a real, identifiable person in sexual or deceptive imagery, and keeps face-reference tools for fictional and original characters.
- `nero-card` and `nero-context` do not convert or compress sexual content involving minors or childlike figures, convert cards built on a real person's likeness as SFW only, and add explicit adult ages where missing.

## [1.4] - 2026-11-03

### Added

Five new agents, each following the suite pattern (Core Directives, Quick/Standard/Deep depths, Compact Block, multimodal input and output, SFW/NSFW/Auto modes, removable adult modules, and hand-offs). The suite grows from 19 to **24 agents**.

- **`nero-history`** (`worldbuilding/nero-history.md`): timelines, eras, and shaping events written as causal chains (causes, winners and losers, immediate and long-term consequences), with a Mermaid causal-chain diagram. Separates the official version, the folk version, and the truth; covers legacies, generational memory, lost knowledge, counterfactuals, in-world primary sources, and explicit links to characters, factions, and places. Optional dynasties-and-intimate-history module.
- **`nero-romance`** (`characters/nero-romance.md`): relationships between characters. Chemistry, perspectives and tells, a power map (social, material, emotional, informational, physical), a tension engine, arc beats with triggers, a 0 to 5 heat track, scene ideas, and roleplay rules for the AI. Modules for slow-burn, enemies-to-lovers, forbidden, arranged, tense, toxic, redemptive, found-family, and open relationships. The optional **intimacy module works at the pair level** (compatibility, negotiation, escalation ladder, aftermath) and defers each person's individual profile to `nero-character`.
- **`nero-villain`** (`characters/nero-villain.md`): antagonists with depth. Motivation (including what the villain is right about), methods and style, resources and weaknesses, a personal relationship with the protagonist, a **proactive phased plan** with progress clocks, a Villain Moves table, reaction rules, and lieutenants, plus presentation, arc end states (redemption, fall, tragic, ambiguous, or none), rules for playing the villain, and an optional seductive/dark-romance module.
- **`nero-scenario`** (`adventure/nero-scenario.md`): opening scenes, first messages, situational hooks, and cold opens. Defines an anatomy (anchor, situation, pressure, presence, open door), an opening-type table, length and narration settings, a Situation Sheet, a Scenario line for cards, and an optional intimate-opening module. Distinguished from `nero-narrative` (broad prose) and `nero-jps` (platform cards).
- **`nero-sandbox`** (`adventure/nero-sandbox.md`): open-world and hexcrawl packs. Premise, hex map and hex key (aligned to uploaded maps), hub and danger gradient, points of interest, rumor tables, travel and exploration rules, random encounter/discovery/event tables, resource and threat progress clocks, faction turns, rewards, and an **Exploration Directive** for AI-run play. Optional roadside-intimacy module.

### Changed

- The *NERO suite* table inside the Core Directives of **every agent** now lists the five new agents. Core Directives remain identical in all 24 files.
- The `Version` field in every prompt header moved from `1.3` to `1.4`.
- Hand-offs: each new agent hands off to `nero-worldbuilding`, `nero-character`, `nero-multi-character`, `nero-adventure`, `nero-narrative`, `nero-combat`, and `nero-factions`, among others. The existing agents `nero-worldbuilding`, `nero-character`, `nero-multi-character`, `nero-adventure`, `nero-narrative`, `nero-combat`, `nero-factions`, `nero-places`, `nero-cultures`, and `nero-creatures` now point to the relevant new agents.
- `README.md` and `README.pt-BR.md` updated: agent count (19 to 24), repository tree, agent tables, workflow diagram, and version table.

## [1.3] - 2026-11-03

### Added

Five new agents, each following the suite pattern (Core Directives, Quick/Standard/Deep depths, Compact Block, multimodal input and output, SFW/NSFW/Auto modes, removable adult modules, and hand-offs). The suite grows from 14 to **19 agents** and from four to six folders.

- **`nero-factions`** (`worldbuilding/nero-factions.md`): guilds, noble houses, cults, corporations, gangs, orders, secret societies, and governments. Covers identity, public versus true goals, hierarchy and real power, resources and vulnerabilities, goals and methods, relations with other factions, propaganda, recruitment, internal secrets (a secrets ledger), key figures, and progress clocks. Includes a **Mermaid relations diagram** (open and secret relations) and an optional org chart.
- **`nero-magic`** (`worldbuilding/nero-magic.md`): magic, superpowers, mystic arts, divine power, psionics, and arcane technology. Defines source, laws, costs, limits and failure tables, schools and traditions, progression with a power ceiling, access, practice and sensory signature, risks, the culture and economy around power, sample techniques, and an optional intimate-power module. Supports hard and soft systems.
- **`nero-cultures`** (`worldbuilding/nero-cultures.md`): peoples and societies from the inside. Covers values and worldview, customs and etiquette, taboos and law, festivals and rites, family and kinship, a language sketch with naming tables, aesthetics, the sacred, the body, outsiders, internal diversity, an optional intimacy-and-sexuality module, and a "Playing a Member" guide. Includes explicit guidance against stereotypes.
- **`nero-creatures`** (new `creatures/` folder): beasts, monsters, fantastical animals, constructs, spirits, undead, and aberrations. Covers ecology, behavior, a combat profile that shares the generic stat block of `nero-combat`, weaknesses and counters, loot and harvest, folklore (belief versus truth), variants, and encounter tables. Works in **Design Mode** and **Run Mode** (plays the creature live). The optional mature module is limited to sapient adults.
- **`nero-lorebook`** (new `tools/` folder): turns any material, including output from the other agents, into optimized lorebook entries for SillyTavern, Agnai, and similar frontends. Prioritizes tokens, keywords and secondary keys, trigger planning, order, recursion, and budget. Every entry comes in **Compact** and **Full** versions, with an Activation Plan, a budget summary, and optional JSON export (Character Card V2 `character_book` or a generic array).

### Changed

- The *NERO suite* table inside the Core Directives of **every agent** now lists the five new agents. Core Directives remain identical in all 19 files.
- The `Version` field in every prompt header moved from `1.2` to `1.3`.
- Hand-offs: `nero-worldbuilding`, `nero-multi-character`, `nero-adventure`, `nero-combat`, and `nero-character` now point to the relevant new agents, and each new agent hands off to all five of them (and to the rest of the suite where relevant).
- `README.md` and `README.pt-BR.md` updated: agent count (14 to 19), repository tree, agent tables, the workflow diagram, and the version table.

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

[1.5]: https://github.com/KMC1525/nero/releases/tag/v1.5
[1.4]: https://github.com/KMC1525/nero/releases/tag/v1.4
[1.3]: https://github.com/KMC1525/nero/releases/tag/v1.3
[1.2]: https://github.com/KMC1525/nero/releases/tag/v1.2
[1.1]: https://github.com/KMC1525/nero/releases/tag/v1.1
[1.0]: https://github.com/KMC1525/nero/commit/76056bac08a9b40875bd651f1afe80284abe940a
