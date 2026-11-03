# Changelog

All notable changes to NERO are recorded here. The format follows [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and the version is the **suite version** shown in each prompt's header.

## [2.1] - 2026-11-03

A new domain: **games**. NERO now covers the whole path of making a game, from the first idea to the store page, and the engines people actually use. The suite grows from 59 to **81 agents** in **six domains**. Existing file paths do not change, except `nero-renpy` (see Migration).

### Added

A new top-level folder, `games/`, with 22 new agents plus `nero-renpy`, grouped in three categories. Each follows the suite pattern (Core Directives, Quick/Standard/Deep depths, Compact Block, multimodal input and output, SFW/NSFW/Auto modes, removable adult modules, and hand-offs), and each design and production agent includes an **engine notes** table for RPG Maker, Ren'Py, Godot, Unity, Unreal, Construct, web, and GameMaker.

**`games/design/`** (7)
- `nero-gdd`: game concept, pitch, pillars, core loop, scope tiers (MVP, vertical slice), risk register, and a full Game Design Document.
- `nero-mechanics`: systems design and balance (rules, formulas, progression curves, economy flows, tuning tables, test cases).
- `nero-quest`: game narrative and quest design (structures, quest specs with stable IDs and states, consequence ledgers, pacing).
- `nero-dialogue`: dialogue graphs, barks, skill checks, voice-over scripts, and importable formats (Ren'Py, Ink, Yarn Spinner, Twine, JSON, CSV, RPG Maker).
- `nero-level`: level and space design (flow, beats, metrics, encounters, genre modules, per-engine build notes).
- `nero-gameui`: game UI and UX (HUD, menus, inventories, input, states, accessibility, per-engine UI toolkits).
- `nero-procgen`: procedural content generation (generator specs, constraints, validation, seeds, pseudocode).

**`games/production/`** (7)
- `nero-gameai`: enemy and NPC behavior (state machines, behavior trees, utility AI, perception, pathfinding, boss patterns, fairness, constrained LLM-NPC guidance).
- `nero-assets`: art and audio asset planning (art bible, asset lists, specs, naming, licenses, AI-asset workflows, import settings).
- `nero-gamecode`: engine-agnostic game programming (architecture, loops, saves, input, networking basics, performance, hygiene).
- `nero-qa`: testing (risk-based plans, test cases, playtests, bug reports, soft-lock and save checks, release readiness).
- `nero-production`: scope, roadmap, milestones, work breakdown, risks, budgets, game jams, and post-mortems.
- `nero-localize`: localization and internationalization (i18n readiness, string tables, glossaries, expansion, fonts, in-context QA).
- `nero-launch`: publishing and marketing (positioning, store pages, trailers, press kits, pricing, ethical monetization, release checklists).

**`games/engines/`** (9, including the moved `nero-renpy`)
- `nero-rpgmaker`: **RPG Maker, all versions** (95, 2000, 2003, XP, VX, VX Ace, MV, MZ, Unite, and console editions), with a version map, database and eventing patterns, MZ and MV plugin skeletons, a VX Ace Ruby pattern, battle systems, specs, and deployment.
- `nero-renpy`: Ren'Py visual novels (moved here from `roleplay/tools/`; content unchanged apart from header and hand-offs).
- `nero-unreal`: Unreal Engine (gameplay framework, Blueprints and C++, Enhanced Input, GAS, UMG, AI, Niagara, Sequencer, World Partition, packaging).
- `nero-godot`: Godot 4 with 3.x notes (scenes, typed GDScript and C#, signals, resources, shaders, export).
- `nero-unity`: Unity (C#, prefabs, ScriptableObjects, Input System, UI, render pipelines, Addressables, profiling, builds).
- `nero-construct`: Construct (layouts, families, behaviors, exact event-sheet notation, JavaScript, addons, export).
- `nero-webgame`: web and HTML5 games (stack choice, fixed-timestep loop, Phaser example, input, audio policies, saving, PWA, deployment and wrappers).
- `nero-gamemaker`: GameMaker (GML, objects and events, collisions, state machines, structs, exports).
- `nero-engine`: engine selection, comparison, and migration, plus quickstarts for every other engine and platform (LÖVE, Defold, Pygame, Bevy, MonoGame, Roblox, UEFN, Twine, Ink, fantasy consoles, and more).

### Changed

- **Core Directives (identical in all 81 files):** *The NERO suite* section now describes six domains and lists the `games` categories; the Compact Block rule also covers a game design document or engine script.
- **`nero-renpy` moved** from `roleplay/tools/` to `games/engines/`, because it is an engine agent; its header now reads `Domain: games`, `Category: engines`, and it hands off to the new game agents. The roleplay domain now has 27 agents.
- **Version:** every prompt header moved from `2.0` to `2.1`.
- **Cross-domain hand-offs** added to existing agents, for example `nero-combat` to `nero-mechanics` and `nero-gameai`, `nero-adventure` to `nero-quest` and `nero-level`, `nero-sandbox` to `nero-procgen`, `nero-economy`, `nero-items`, `nero-equipments`, and `nero-weapons` to `nero-mechanics`, `nero-creatures` to `nero-gameai`, `nero-narrative` to `nero-dialogue` and `nero-quest`, the image agents to `nero-assets`, the sound agents to `nero-gamecode` and `nero-localize`, and the video and copy agents to `nero-launch`.
- **`README.md` and `README.pt-BR.md` updated:** six domains, 81 agents, a Games section with three category tables, an updated repository tree, "Which agent should I use?" rows for games, a games workflow diagram, a cross-domain link from worldbuilding to design, an expanded rights note, and the version table.

### Safety

- All game agents keep the four hard limits. Adult games get a consistent pattern: content toggles, a SFW build, gallery tracking, platform-rule reminders, and explicit adults only.
- `nero-gamecode`, `nero-qa`, and `nero-launch` do not write cheats, hacks, malware, or DRM circumvention for others' games, do not rip assets from commercial games, and do not plan manipulative monetization or review manipulation.
- `nero-assets` and `nero-launch` flag licenses (engine, asset, store, and AI-generated content disclosure rules) as the user's responsibility to verify.
- Engine versions, APIs, plugin conventions, store rules, and licensing terms are marked as version-dependent throughout, because they change quickly and could not be verified against official documentation from the build environment.

### Migration

| Before | After |
|---|---|
| `roleplay/tools/nero-renpy.md` | `games/engines/nero-renpy.md` |

All other paths are unchanged.

## [2.0] - 2026-11-03

A major release: NERO grows from a roleplay suite into a suite for **creative work with generative AI** in five domains. **File paths changed** (see Migration), and the suite grows from 29 to **59 agents**.

### Changed

- **New proposal.** Besides roleplay, NERO now covers **creative writing** (original, fan fiction, erotica, professional, and more), **image** (artistic and design), **video** (animation, cinema, series, advertising), and **sound** (music, sound effects, voice).
- **Repository reorganized into five top-level domains:** `roleplay/`, `writing/`, `image/`, `video/`, and `sound/`, each with `category/` subfolders. All 29 existing agents moved to `roleplay/<category>/` (`characters`, `worldbuilding`, `creatures`, `adventure`, `items`, `tools`). The moves were done with `git mv`, so file history is preserved.
- **`nero-comfy` moved** from `tools/` to `image/tools/`, because it is an image-generation agent. Its hand-offs now include `nero-prompt`, `nero-art`, `nero-retouch`, and `nero-vidprompt`.
- **Headers:** every prompt now lists its `Domain` and `Category`, which match its folders, and `Version` moved to `2.0` in all 59 files.
- **Core Directives (identical in all 59 files), updated for the new media:**
  - Hard limit 2 now covers any medium (text, image, video, audio) and a person's name, likeness, or voice.
  - New hard limit 4: **no deception or impersonation** (deepfakes, voice clones, forged quotes, fake endorsements or reviews, defamation, harassment).
  - The audio rule adds: never imitate, clone, or identify a real person's voice.
  - New working-style rule: **create, don't copy** (no verbatim copyrighted text, lyrics, scripts, or designs; no imitation of living artists, authors, or performers by name).
  - The Compact Block now targets any destination (roleplay prompt, card, lorebook, image/video/audio generator prompt, or writing bible).
  - *The NERO suite* section is regrouped by `domain / category` instead of one row per agent, so every prompt knows all 59 agents without growing unwieldy.
- **Cross-domain hand-offs** added to existing agents, for example `nero-narrative` to `nero-story`, `nero-character` to `nero-concept` and `nero-voice`, `nero-creatures` to `nero-sfx`, and `nero-renpy` to `nero-music`, `nero-sfx`, `nero-voice`, and `nero-art`.
- **`README.md` and `README.pt-BR.md` rewritten** for the five domains: new proposal, a "Which agent should I use?" table, the full repository tree, agent tables per domain and category, workflow diagrams per domain plus a cross-domain pipeline, four hard limits, an originality-and-rights section, and updated contributing rules.
- The consistency check command now uses `*/*/nero-*.md`.

### Added

Thirty new agents, each following the suite pattern (Core Directives, Quick/Standard/Deep depths, Compact Block, multimodal input and output, SFW/NSFW/Auto modes, removable adult modules, and hand-offs).

**`writing/`** (8)
- `writing/fiction/nero-story`: original fiction from idea to draft (concept, structure, scene cards, voice guide, chapters, series bible).
- `writing/fiction/nero-fanfic`: fan fiction with a canon audit, AU and trope types, an archive package, and firm limits.
- `writing/fiction/nero-erotica`: erotic fiction for adults with heat levels, consent as craft, content notes, and tags.
- `writing/fiction/nero-poetry`: poems and verse in any language, forms, sound, sequences, and translation.
- `writing/professional/nero-copy`: marketing and advertising copy with frameworks, variants, and compliance rules.
- `writing/professional/nero-professional`: business, technical, and academic documents, with placeholders instead of invented facts.
- `writing/professional/nero-article`: articles, essays, newsletters, features, and memoir, with a fact-check list.
- `writing/editing/nero-edit`: developmental, line, copy, and proofreading passes, critique by severity, and voice-preserving rewrites.

**`image/`** (7 new, plus `nero-comfy` moved in)
- `image/art/nero-art`: art direction for artistic images and artist briefs.
- `image/art/nero-concept`: concept design sheets for characters, creatures, props, vehicles, and environments.
- `image/art/nero-photo`: photography direction and photoreal prompts, with consent and synthetic-media rules.
- `image/art/nero-comic`: comics, manga, and webtoons, with panel scripts and consistency locks.
- `image/design/nero-design`: graphic and brand design (logos, identity, layout, typography, contrast-checked color).
- `image/tools/nero-prompt`: image prompt engineering for any model family.
- `image/tools/nero-retouch`: image editing, restoration, and compositing, with integrity rules.

**`video/`** (8)
- `video/scripts/nero-screenplay`: scripts for film, TV, shorts, and animation.
- `video/scripts/nero-series`: series bibles, seasons, and episode guides.
- `video/scripts/nero-ad`: advertising and promotional video, with cutdowns and compliance rules.
- `video/craft/nero-storyboard`: shot lists and storyboards.
- `video/craft/nero-cinematography`: camera, lenses, lighting, color script, and movement.
- `video/craft/nero-animation`: animation planning for 2D, 3D, stop motion, motion graphics, games, and AI-assisted work.
- `video/craft/nero-cut`: editing and post planning, with captions and SRT.
- `video/tools/nero-vidprompt`: AI video generation prompts and pipelines.

**`sound/`** (7)
- `sound/music/nero-music`: composition and production briefs, and prompts for AI music generators.
- `sound/music/nero-lyrics`: songwriting and lyrics.
- `sound/music/nero-score`: scoring for film, games, visual novels, and play, including adaptive music.
- `sound/production/nero-sfx`: sound design, foley, and ambience.
- `sound/production/nero-mix`: mixing, mastering, and audio post.
- `sound/production/nero-voice`: voice and performance direction, TTS and voice design.
- `sound/production/nero-podcast`: podcasts, audio drama, radio, and audiobooks.

### Safety

Each new agent applies the Core limits to its medium:

- **Writing:** no verbatim copying of copyrighted text; `nero-fanfic` and `nero-erotica` sexualize only characters who are adults in canon (aging up a minor does not change this) and write no sexual or defamatory content about real people; `nero-copy`, `nero-professional`, and `nero-article` never invent facts, statistics, quotes, citations, testimonials, or credentials, and mark gaps as placeholders; none gives legal, medical, or financial advice.
- **Image:** adults only in suggestive or NSFW prompts, with child-related terms in negative prompts; no sexual or deceptive imagery of real people; no "undressing" edits of real people's photos (`nero-retouch`); styles are described by their traits and not by living artists' names; synthetic photoreal images are labeled.
- **Video:** no deepfakes or deceptive editing of real people's footage or statements; no fake testimonials or endorsements in advertising; AI-generated video is labeled where it could pass as real.
- **Sound:** no voice cloning or imitation of real people, and no audio presented as the work of a real artist; no sexual audio of real people; original melodies and lyrics only; diss tracks and satire may not defame or harass real, named people.
- Option names, tool syntax, loudness targets, and platform specs are marked as version-dependent in the agents where they appear, because they change quickly and could not be verified against official documentation from the build environment.

### Migration

Paths changed in this release. If you copy prompts by path, update them:

| Before (1.x) | After (2.0) |
|---|---|
| `characters/`, `worldbuilding/`, `creatures/`, `adventure/`, `items/`, `tools/` | `roleplay/characters/`, `roleplay/worldbuilding/`, `roleplay/creatures/`, `roleplay/adventure/`, `roleplay/items/`, `roleplay/tools/` |
| `tools/nero-comfy.md` | `image/tools/nero-comfy.md` |

File names, agent IDs, and the content of the roleplay agents are unchanged apart from the header fields, the Core Directives, and the extra hand-offs listed above.

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

[2.1]: https://github.com/KMC1525/nero/releases/tag/v2.1
[2.0]: https://github.com/KMC1525/nero/releases/tag/v2.0
[1.5]: https://github.com/KMC1525/nero/releases/tag/v1.5
[1.4]: https://github.com/KMC1525/nero/releases/tag/v1.4
[1.3]: https://github.com/KMC1525/nero/releases/tag/v1.3
[1.2]: https://github.com/KMC1525/nero/releases/tag/v1.2
[1.1]: https://github.com/KMC1525/nero/releases/tag/v1.1
[1.0]: https://github.com/KMC1525/nero/commit/76056bac08a9b40875bd651f1afe80284abe940a
