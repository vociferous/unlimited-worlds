# REQ-001 — Game HUD (In-Play Persistent Overlay)

**Domain:** UI/HUD
**GDD Reference:** Section 2.1 (Phase 1: Read), Section 2.3 (Phase 3: Mark), Section 3.3 (Strata Depth), Section 4.2 (Terrain Stance System), Section 6.2 (Claim Stakes), Section 7.2 (Historical Ledger)
**Phase Relevance:** Phase 1
**Source Session:** GDD-v0.1 (primary), Mechanic Designer Session 001 (core loop, Terrain Stance, Strata), World Architect Session 001 (faction identity, Varek Delta biome)
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

1. Geological State Indicator: shows the current zone's geological state descriptor (e.g., "Salt Flat — Tidal Active" or "River Delta — Tectonic Stable"). Must show at minimum: zone name, geological classification, and a visual activity indicator (calm / active / precursor event).
2. Active Terrain Stance Display: shows whether a Terrain Stance is currently active, which stance (e.g., "Varekian Salt Attunement — ACTIVE"), and a visual indicator of stance benefits currently in effect. If no stance is active, shows the stances available for the current terrain type and the Strata depth required to activate each.
3. Strata Depth (Discipline Progress): compact display of the player's primary discipline and current Strata tier (Surface / Formation / Mantle / Core) with a progress bar or depth indicator within that tier. Must show the discipline name (e.g., "Reading — Formation Understanding, Strata 14").
4. Faction Ledger Notification Badge: a notification badge showing unread Historical Ledger entries since last check. Must show count, a brief last-entry preview on hover/expansion, and a visual state for "new entries since you logged in."
5. Claim Stake Timer: if the player has an active Claim Stake, shows a countdown timer (72-hour max) and the stake's location label. Shows "UNDEFENDED" warning if the 12-hour undefended window is approaching in a contested zone. Hidden if no active Claim Stake.
6. Basic Resource Inventory: compact count display for the player's primary gathered resource categories (raw materials in inventory). Must show at least 3–4 resource slots with quantity. Designed for at-a-glance reading, not a full inventory panel.
7. All elements must be legible at 1920×1080 without obscuring the game world. The HUD should occupy screen edges/corners and have a clear spatial logic.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact (default starting faction). Materials: aged timber, polished river stone, brass fittings, salt crystal accents, rope and pulley hardware. This HUD is the Varekian Compact faction's UI skin — the default for all new players arriving in the Varek Delta.

**Color guidance:**
- Tidal grey-green: #7a9e8e (primary UI background panels)
- Aged brass: #b5894f (borders, dividers, active state indicators)
- Salt-flat white: #e8e4d9 (primary text)
- Deep river brown: #3d2b1f (panel backgrounds, dark zones)
- Verdigris accent: #5a8a7a (secondary highlights, hover states)
- Alert/warning states: use a muted amber (#c49a2f) not red; geological warning is mineral, not emergency

**Tone:** Pragmatic mercantile-ledger aesthetic. Information-dense. Tabular where possible. Nothing decorative that is not load-bearing. Aged document texture on panels (subtle paper/parchment grain, not heavy distress). The HUD should feel like a working sailor's instrument panel, not a fantasy UI chrome.

**Anti-patterns:**
- No glowing magical runes or arcane energy effects
- No floating UI elements without physical grounding (all panels should look anchored, bracketed, or mounted)
- No purple/void magic color language
- No generic fantasy gold filigree
- No large empty decorative areas — every pixel earns its place
- Avoid high-contrast neon highlighting; all active states should feel like warm light through brass, not electric glow

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world whose geology is its metaphysics. The world is a geological fantasy — no divine magic, no arcane energy. Power comes from understanding and working with geological forces: tectonic movement, volcanic activity, karst cave systems, river delta dynamics. The world is still recovering from an event 400 years ago called the Fracturing, when the geological suppression systems of an ancient civilization (the Founders) failed, causing continents to crack and reform.

The core gameplay loop is Read → Act → Mark: players observe the world's geological and political state, take actions that change it, and leave traceable marks. The world is truly persistent — player actions enter a civilizational Historical Ledger and shape NPC behavior and faction memory.

Four civilizations exist:
- THE VAREKIAN COMPACT: Delta and river basin people. Pragmatic merchants and engineers. Survived the Fracturing by adaptation. They want to re-establish trade routes and predict geological change commercially. Visual identity: aged timber, polished river stone, brass fittings, salt crystal accents. Palette: tidal grey-green (#7a9e8e), aged brass (#b5894f), salt-flat white (#e8e4d9), deep river brown (#3d2b1f), verdigris accent (#5a8a7a). UI tone: mercantile-ledger, information-dense, tabular, nothing decorative that is not functional, aged document texture.
- THE ASHBOUND: Volcanic plateau people. Militaristic theocrats who consider the Fracturing a divine selection event. Visual identity: volcanic basalt, obsidian, forge iron, compacted ash. Palette: deep volcanic black (#1a1208), forge orange (#d4580a), ash grey (#6b6359), blood-oxide red (#8b1a0f).
- THE DEEPWALKERS: Underground karst civilization. Ancient, patient, scholarly. Live in bioluminescent cave systems. Visual identity: shaped limestone, bioluminescent mineral veins, cave crystals. Palette: deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f), pale limestone (#d4cdb8).
- THE TIDE COMPACT: Island and coastal confederation. Young, meritocratic, exploratory. Visual identity: weathered hardwood, hemp rope, salvaged metal, oilskin. Palette: storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a), sea-glass green (#5a9e8a).

Player progression uses a Geological Discipline system — four disciplines aligned to factions (Reading/Varekian, Shaping/Ashbound, Resonance/Deepwalker, Charting/Tide Compact). Progression is measured in Strata depth: Surface Understanding (1–10), Formation Understanding (11–25), Mantle Understanding (26–40), Core Understanding (41–50).

Combat uses a Terrain Stance system: players read the zone's geological state and activate stances that change combat behavior. Varekian Salt Attunement activates on salt crystal terrain; Ashbound Volcanic Stance on obsidian; Deepwalker Deep Sense underground; Tide Compact Open Water Stance near coastal water. Stance activation requires a 3-second channel.

The Historical Ledger is a public faction event log — the last N significant events for each faction, visible at notice boards in town centers and via a UI panel. It drives NPC dialogue and player reputation. Events age out into a Legend Layer of oral tradition and monuments.

Claim Stakes are 72-hour temporary resource priority markers, visible in the world and on maps. A stake in a contested zone triggers a Contention Event if undefended for 12 consecutive hours.

DESIGN SURFACE:
The in-play persistent HUD overlay for a player currently in the Varek Delta, playing a Varekian Compact-aligned character. This HUD is the default faction skin for all new players. It must be present during normal gameplay at all times without obscuring the world. Design this as a screenshot of the HUD overlaid on a simple placeholder background (a flat dark teal-grey background representing the game world is fine — the focus is the HUD elements).

FUNCTIONAL REQUIREMENTS:
1. Geological State Indicator (top-left or top-center region): Shows current zone name ("Varek Delta — Eastern Salt Flats"), geological classification, and a visual activity indicator. Use a small graphical motif — perhaps a layered strata icon or a simple tide marker. Current state for this mockup: "Tidal Active — Minor tremor precursor detected." Show this as a mild warning state (not emergency).
2. Active Terrain Stance Display (left side or bottom-left): The player has NO stance currently active. Show the available stances panel collapsed to a narrow indicator showing "Varekian Salt Attunement available — Formation depth required" and "STANCE: INACTIVE." The panel should suggest it can expand on interaction.
3. Strata Depth Display (somewhere compact — bottom-left or left edge): Player is "Reading — Formation Understanding — Strata 17 of 25." Show a depth indicator styled like a geological cross-section or depth gauge, not a standard XP bar. The Strata tier name should be prominent.
4. Faction Ledger Badge (top-right): Shows "3 new Ledger entries" since last check. On the badge/panel, show a preview of the most recent entry: "VAREKIAN COMPACT — Northern Channel: Sandbar formation confirmed — Merchant transit delayed 2 days." Badge should feel like a notice pinned to a board, not a notification bell.
5. Claim Stake Timer (right side, visible): Player has an active Claim Stake. Show: "CLAIM ACTIVE — Eastern Salt Node 7 — 61h 22m remaining." Include a small map indicator dot. No warning state currently (stake is defended).
6. Resource Inventory Strip (bottom edge or bottom-right): Show 4 resource slots with amounts:
   - Salt Crystal: 47 units
   - River Stone: 12 units
   - Reed Fiber: 8 units
   - Brass Fittings (crafted): 3 units
   Icons should be geological/material in character — not fantasy gems.
7. All HUD elements use the Varekian Compact visual identity (see Visual Constraints below).

VISUAL CONSTRAINTS:
Faction: Varekian Compact.
Materials palette reference: aged timber, polished river stone, brass fittings, salt crystal accents, rope and pulley hardware.
Colors: tidal grey-green (#7a9e8e) for panel backgrounds, aged brass (#b5894f) for borders and active indicators, salt-flat white (#e8e4d9) for primary text, deep river brown (#3d2b1f) for dark panel backgrounds, verdigris accent (#5a8a7a) for secondary highlights. Warning amber (#c49a2f) for mild alert states.
Tone: Pragmatic mercantile-ledger aesthetic. Information-dense. Tabular layout where possible. Nothing decorative that is not functional. Subtle aged paper/parchment texture on panels. Feels like a working sailor's instrument panel crossed with a merchant ledger.
Anti-patterns: No glowing arcane runes. No floating UI without physical grounding — all panels look anchored, bracketed, or bolted. No purple/void magic color. No generic fantasy gold filigree. No neon highlighting — active states feel like warm brass lamp light, not electric glow. No large empty decorative spaces.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use realistic representative placeholder data (not "Lorem ipsum") — use the data specified above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-001-game-hud.html`
