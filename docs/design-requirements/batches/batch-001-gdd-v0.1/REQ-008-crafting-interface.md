# REQ-008 — Crafting Interface

**Domain:** Menu/Screen
**GDD Reference:** Section 5.2 (Crafting), Section 3.1 (The Four Disciplines — especially Resonance/Shaping), Section 5.1 (Gathering — origin geology metadata)
**Phase Relevance:** Phase 2
**Source Session:** Mechanic Designer Session 001 (Question 5: Economy Loop — Crafting Subsystem), GDD-v0.1 Section 5.2
**Batch:** batch-001-gdd-v0.1
**Created:** 2026-06-02

---

## Human Review Status

- [ ] APPROVED — ready for Claude artifact generation
- [ ] REVISED — see notes below
- [ ] DEFERRED — reason below

**Review notes:**
<!-- Human fills this in during review -->

---

## Functional Requirements

1. Three-tier crafting structure visible: Tier 1 (Raw Processing), Tier 2 (Geological Crafting), Tier 3 (Synthesis). The player's current discipline depth gates access — show one tier fully accessible and the others in locked/preview states appropriate to the player's progress.
2. Origin geology metadata display on all materials in inventory/input: every material shows where it came from (biome, zone, geological formation type). This is mechanically meaningful — the same ore from the Scorch Plateau has different properties than ore from the Shatter Coast. Materials must carry this tag visibly.
3. Recipe discovery state: recipes are not bought from vendors or dropped. They are discovered through world interaction. Show three recipe discovery states: fully known (player has discovered this recipe), partially known (player has found the pattern but not all materials), and undiscovered (shown as geological research hooks — "Something with these mineral characteristics should produce...").
4. Synthesis multi-biome slot display (Tier 3): the Synthesis recipe input requires materials from at least two distinct biome types. The input slots must visually communicate this requirement — different biome-origin slots with geological material cues, and a "biome conflict" or "biome combination" result indicator.
5. The crafting output must show origin-geology properties on the output item — not just the item name, but a geological property summary (e.g., "Volcanic obsidian — fire-affinity, high durability in heat environments, brittle in cold").
6. The interface must be accessible from a crafting station in the world — it is a menu panel that opens at a crafting facility, not a floating UI accessible anywhere.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact (default player faction). The crafting interface uses the mercantile-ledger aesthetic — tabular layout, information-dense, origin-geology metadata displayed as ledger annotations. Materials are catalogued with geological precision.

**Color guidance:** Tidal grey-green (#7a9e8e) for panel backgrounds, aged brass (#b5894f) for borders and tier dividers, salt-flat white (#e8e4d9) for primary text, deep river brown (#3d2b1f) for locked tier panels, mineral amber (#c49a2f) for discovery state indicators, verdigris (#5a8a7a) for secondary highlights.

**Origin geology metadata display:** Each material should carry a small geological origin badge (biome color coding): Varek Delta — tidal grey-green; Scorch Plateau — forge orange (#d4580a); Deepwalker Karst — mineral amber (#c49a2f); Shatter Coast — storm grey-blue (#4a6b7a). The biome badge makes at-a-glance material origin legible.

**Tone:** A craftsperson's workshop ledger. The interface should feel like a working geological instrument — technical, annotated, material-specific. Not a fantasy magic crafting UI with mystical glows. The output quality comes from knowledge and geological understanding, not from magical sparks.

**Anti-patterns:**
- No glowing crafting animations (no magical blue orbs, no sparkle effects)
- No generic MMO crafting UI (list of recipes on left, materials on right, big combine button)
- Origin geology metadata must not be hidden in tooltips — it should be immediately visible on material items
- No purple magic visual language

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath, a world of geological fantasy. The economy is grounded in geography: resources are extracted from specific geological locations, transformed through geological crafting, and traded across physically located markets. Every stage of the crafting process expresses geological identity.

THE CRAFTING SYSTEM — three tiers:
TIER 1 — RAW PROCESSING: Convert extracted materials into workable stock (ore to ingots, mineral formations to powders, biological materials to alchemical bases). Requires basic faction infrastructure. Any player can do this. Origin geology metadata is preserved but does not affect Tier 1 output properties.
TIER 2 — GEOLOGICAL CRAFTING: Apply discipline knowledge to produce goods with properties derived from their origin geology. Requires Formation Understanding in any relevant discipline; Tier 2 facility. A blade crafted from Scorch Plateau obsidian has fire-affinity properties (increased fire damage on hit; higher durability in heat environments; brittle in cold). The same blade crafted from Shatter Coast mineral deposits has salt-corrosion resistance. Two items made from the same recipe but different origin geologies are mechanically non-identical.
TIER 3 — SYNTHESIS: Combine materials from two or more distinct geological sources to produce hybrid materials with properties neither source material has alone. Requires Mantle Understanding in at least one discipline; Synthesis facility (major faction capitals or high-development player settlements); materials sourced from at least two distinct biome types. A Resonance practitioner synthesizing Deepwalker rare minerals with Ashbound volcanic ore produces materials no single-source process can replicate. Synthesis recipes are geological knowledge — discovered through world interaction, not dropped items. The discoverer's name is attributed in the Historical Ledger. Knowledge can be shared, sold, or kept secret.

GEOLOGICAL DISCIPLINES (related to crafting access):
Reading (Varekian Compact): geological intelligence. Enables geological survey before extraction, material quality assessment.
Shaping (Ashbound): terrain manipulation. Enables blast extraction, structural crafting, mine development.
Resonance (Deepwalker): geological resonance. Full Synthesis capability at Mantle depth. Anchor installation interface.
Charting (Tide Compact): geographical mastery. Exploration bonuses, first-finder advantages, salvage expertise.

Strata depth: Surface Understanding (1–10), Formation Understanding (11–25), Mantle Understanding (26–40), Core Understanding (41–50). Tier 2 requires Formation; Tier 3 requires Mantle.

FOUR BIOMES and their material register:
- VAREK DELTA: salt crystal, river stone, reed fiber, alluvial clay, freshwater minerals. Palette marker: tidal grey-green (#7a9e8e).
- SCORCH PLATEAU: volcanic obsidian, forge iron, sulfur compounds, heat-cracked basalt, magma-trace minerals. Palette marker: forge orange (#d4580a).
- DEEPWALKER KARST: rare karst minerals, bioluminescent fungal compounds, cave crystal formations, limestone powder, ancient bone stock. Palette marker: mineral amber (#c49a2f).
- SHATTER COAST: sea glass, salt-corroded iron, waterlogged timber, drowned-ruin salvage, storm-worn granite. Palette marker: storm grey-blue (#4a6b7a).

THE VAREKIAN COMPACT visual identity for this interface:
Materials: aged timber, polished river stone, brass fittings, salt crystal accents.
Palette: tidal grey-green (#7a9e8e) panel backgrounds, aged brass (#b5894f) borders and dividers, salt-flat white (#e8e4d9) text, deep river brown (#3d2b1f) dark panel fills, verdigris (#5a8a7a) secondary highlights, mineral amber (#c49a2f) for discovery/attention states.
Tone: mercantile-ledger aesthetic — information-dense, tabular, annotated, nothing decorative that is not functional. A craftsperson's workshop ledger.

DESIGN SURFACE:
The crafting interface — a menu panel that opens when a player activates a crafting station. The player is a Varekian Compact Reading practitioner at Strata 17 (Formation Understanding). They have access to Tier 1 and Tier 2 crafting. Tier 3 is visible but locked.

FUNCTIONAL REQUIREMENTS:
1. Layout: the interface has three main zones:
   - LEFT PANEL: recipe browser (organized by tier)
   - CENTER PANEL: active recipe / crafting workspace (selected recipe, input material slots, output preview)
   - RIGHT PANEL: player material inventory with origin geology metadata
2. LEFT PANEL — Recipe Browser:
   TIER 1 — RAW PROCESSING (fully accessible):
   Show 3 recipes as example:
   - "River Stone → Cut Stone Blocks" — known
   - "Salt Crystal → Refined Salt Powder" — known
   - "Reed Fiber → Woven Reed Mat" — known
   TIER 2 — GEOLOGICAL CRAFTING (accessible, Formation depth met):
   Show 4 recipes:
   - "Obsidian Shard + Forge Iron → Volcanic Blade" — known (discovered)
   - "River Stone + Salt Crystal → Salt-Reinforced Masonry" — known
   - "Cave Crystal + Limestone Powder → Resonance Compound" — partially known (missing one component — show as research state with geological note: "Crystal formation in karst limestone suggests a binding compound — further Karst engagement required")
   - [Undiscovered recipe slot] — show as "Geological pattern detected — Shatter Coast + Varek Delta combination. Properties unknown. Continue surveying."
   TIER 3 — SYNTHESIS (locked — Mantle depth required):
   Show 2 locked recipes as preview:
   - "Deepwalker Rare Mineral + Ashbound Volcanic Ore → [LOCKED — Mantle Understanding required]"
   - "Multi-biome synthesis slot — [LOCKED]"
   Locked tier uses visual treatment showing the recipes exist but are inaccessible.
3. CENTER PANEL — Crafting Workspace:
   Show the "Volcanic Blade" recipe (Tier 2) selected:
   - Recipe name: "Volcanic Blade"
   - Recipe source: "Discovered at Scorch Plateau border survey — attributed: [Player]"
   - Input slots: two material input slots
     SLOT 1: Obsidian Shard — filled with: "Obsidian Shard × 2 / Origin: Scorch Plateau, Eastern Obsidian Field, Ashbound Territory / Geological class: Volcanic extrusive / Property: Fire-affinity, Heat-durability, Cold-brittle"
     SLOT 2: Forge Iron — filled with: "Forge Iron × 1 / Origin: Scorch Plateau, Western Mines / Geological class: High-temperature iron / Property: Heat-tempered, Magnetic resistance"
   - Output preview: "Volcanic Blade (Tier 2) / Properties: Fire-affinity rider on strike / Durability +40% in heat environments / Durability -20% in cold environments / Origin geology: Scorch Plateau (volcanic extrusive class)"
   - A craft action: "Begin Geological Crafting" — styled as a workshop action, not a fantasy button
4. RIGHT PANEL — Material Inventory:
   Show the player's current materials with origin geology metadata as inline annotations. Each item has:
   - Item name
   - Quantity
   - Origin biome (shown as a small color-coded badge using the biome palette markers)
   - One-line geological property note
   Show these specific items:
   - Salt Crystal × 47 | VAREK DELTA | "Tidal boundary crystallization — salt-flat white, high purity"
   - River Stone × 12 | VAREK DELTA | "Alluvial smooth-worn — moderate hardness"
   - Obsidian Shard × 8 | SCORCH PLATEAU | "Volcanic extrusive — fire-affinity, cold-brittle"
   - Forge Iron × 3 | SCORCH PLATEAU | "Heat-tempered ore — magnetic resistance"
   - Cave Crystal × 2 | DEEPWALKER KARST | "Karst crystalline — resonance-sensitive"
   - Sea Glass × 1 | SHATTER COAST | "Storm-smoothed silicate — corrosion resistance"
5. Recipe discovery state visual language:
   - Known recipe: normal display, craft action available
   - Partially known: amber (#c49a2f) indicator, partial recipe shown with geological research note replacing missing components
   - Undiscovered: deep brown panel with geological pattern description — "pattern detected" language, suggesting knowledge is findable in the world
   - Locked (wrong tier/wrong depth): dark panel, lock indicator, "Formation / Mantle / Core depth required" label

VISUAL CONSTRAINTS:
Interface frame: aged timber (#3d2b1f) outer border, aged brass (#b5894f) panel dividers and section headers, tidal grey-green (#7a9e8e) panel backgrounds.
Text: salt-flat white (#e8e4d9) primary, sepia (#7a5c3a) secondary/annotation.
Biome badges: VAREK DELTA = tidal grey-green (#7a9e8e); SCORCH PLATEAU = forge orange (#d4580a); DEEPWALKER KARST = mineral amber (#c49a2f); SHATTER COAST = storm grey-blue (#4a6b7a). Each badge small, colored, with biome name.
Discovery states: mineral amber (#c49a2f) for partially-known; deep brown (#3d2b1f) with reduced text opacity for undiscovered; dark grey with lock symbol for locked tiers.
Tone: craftsperson's workshop ledger. Technical, annotated, material-specific. Geological properties are not flavor text — they are the most important information on screen.
Anti-patterns: no magical glowing crafting effects, no generic MMO crafting UI, no mystery-hidden origin metadata (it must be immediately visible on every material), no fantasy sparkle effects.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific materials, recipes, and geological data given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-008-crafting-interface.html`
