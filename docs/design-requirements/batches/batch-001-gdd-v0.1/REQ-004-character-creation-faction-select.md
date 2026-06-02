# REQ-004 — Character Creation / Faction Selection Screen

**Domain:** Menu/Screen
**GDD Reference:** Section 7.1 (The Four Civilizations), Section 3.1 (The Four Disciplines), Section 8.1 (Onboarding Principles), Section 8.2 (First 30 Minutes — "first consequential choice is faction")
**Phase Relevance:** Phase 1
**Source Session:** World Architect Session 001 (four civilizations, biomes, cultural identities), Mechanic Designer Session 001 (faction-specific disciplines, new player experience), GDD-v0.1 Sections 7.1, 3.1, 8.1
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

1. Full-screen menu presenting all four factions as a consequential first choice. The screen is the player's first experience of the game's depth — it must communicate that these are real civilizations with real trade-offs, not cosmetic skins.
2. Each faction panel must show: faction name, territory/homeland description, primary Geological Discipline, cultural identity summary (2–3 sentences), combat identity summary (1 sentence), and a "recommended for" player archetype note.
3. Visual identity: each faction panel must use its own visual language, materials palette, and architectural motif — the screen is the player's first visual encounter with all four factions simultaneously. The contrast between them should be stark and meaningful.
4. A "Selected" state for exactly one faction (for mockup purposes, the Varekian Compact is selected), showing expanded detail including territory map hint, starting biome name, and the discipline description.
5. A confirmation/commit action — the selection of faction is called out as consequential ("This choice shapes your starting world, discipline access, and faction memory."). Not just an "OK" button.
6. A "no selection yet" state implied — the player can defer faction choice but must understand the consequence (unaffiliated start; no Terrain Stances accessible; no faction Ledger access initially).
7. Character name input field integrated into the screen (not a separate step).
8. The screen header/title should reflect the game's tone — not "Choose Your Class" but something world-grounded ("Where do you come from?" or "Which people are yours?").

---

## Visual Constraints

**Multi-faction layout:** All four factions shown simultaneously in a split or quadrant layout. Each faction occupies its own visual zone with its own palette.

**VAREKIAN COMPACT zone:**
- Palette: tidal grey-green (#7a9e8e), aged brass (#b5894f), salt-flat white (#e8e4d9), deep river brown (#3d2b1f), verdigris (#5a8a7a)
- Motif: platform-city silhouette, horizontal lines, timber and water, salt crystal formations
- Selected state — brighter, panels expand, brass elements glow warmly

**THE ASHBOUND zone:**
- Palette: deep volcanic black (#1a1208), forge orange (#d4580a), ash grey (#6b6359), blood-oxide red (#8b1a0f), obsidian sheen (#2d2520)
- Motif: fortress carved from volcanic rock, vertical imposing forms, obsidian sheen, ember light

**THE DEEPWALKERS zone:**
- Palette: deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f), pale limestone (#d4cdb8), deep water blue (#0a1a2a)
- Motif: karst cave interior, cathedral-scale organic forms, bioluminescent veins in rock, bone-white formations
- Reveals slowly — the Deepwalker panel is the most visually restrained at first glance; depth reveals on attention

**THE TIDE COMPACT zone:**
- Palette: storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a), sea-glass green (#5a9e8a), weathered off-white (#d4cdb8), deep ocean (#0a1a2a)
- Motif: modular ship-like construction, nautical chart elements, weathered hardwood, storm coast, sea glass

**Universal geological base:**
- Deep stone textures throughout the background connecting all four panels
- Geological strata visible in the screen's background architecture
- No floating elements — everything is architecturally grounded

**Tone:** This is the most consequential choice the player makes before entering the world. The screen should communicate weight and permanence. Contrast across the four factions should feel like encountering four genuinely different civilizations, not four color schemes for the same game.

**Anti-patterns:**
- No character appearance customization in this mockup (that is a separate surface) — focus purely on faction choice
- No "recommended" badge that makes one faction look objectively better
- No level/power display that implies difficulty tiers
- No fantasy race selection — these are human-adjacent civilizations differentiated by culture and geography, not species
- Do not make the selection screen look like a game menu — it should feel like arriving at a crossroads in the world

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world of geological fantasy. The world's metaphysics are geological: power comes from understanding the deep forces of the earth — tectonic movement, volcanic activity, karst cave systems, river delta engineering. The world is recovering from the Fracturing, a geological catastrophe 400 years ago when ancient continental suppression systems failed, cracking the single continent into today's fractured geography.

Four civilizations, each born from their geography and carrying deep cultural consequence:

THE VAREKIAN COMPACT:
Territory: The Varek River Delta and lowland river basins. Flooded alluvial plains, shifting sandbars, salt crystal formations, platform cities built above floodplain level.
Cultural identity: Pragmatic merchants and hydraulic engineers. Survived the Fracturing by adaptation — their delta lands flooded rather than cracked. They believe in contracts, information, and knowing the next trade route. No theology. They will negotiate with anyone.
Architecture: Horizontal, modular, low, wide, designed to be relocated if necessary. Cities of layered timber platforms above floodwaters.
Primary discipline: Reading (geological intelligence, resource forecasting, market positioning, trade route optimization).
Combat identity: Control and redirection. Crowd control, terrain manipulation, battlefield debuff. Low direct damage; high strategic depth.
Player archetype: Economy, diplomacy, intelligence, cross-faction access.
Starting zone: The Varek Delta (default for new players).
Visual palette: Aged timber (#3d2b1f), brass fittings (#b5894f), tidal grey-green (#7a9e8e), salt-flat white (#e8e4d9), verdigris (#5a8a7a).
UI tone: Mercantile-ledger aesthetic — information-dense, tabular, aged document texture, nothing decorative that is not functional.

THE ASHBOUND:
Territory: The Scorch Plateau, eastern Dern. A high volcanic plateau with obsidian fields, sulfur vents, and magma-lit underground rivers visible through translucent rock in places.
Cultural identity: Expansionist, militaristic, theocratic. Their homeland rose during the Fracturing — they call it the Ascension and consider themselves divinely selected survivors. They believe the Fracturing is incomplete, that the Dern is being purified of weak lowland civilizations, and that their duty is to assist. Not cartoonish villains — they believe with deep conviction.
Architecture: Cities carved into volcanic rock. Monolithic, fortress-permanent, vertically imposing. Every Ashbound city is a fortress that has been lived in so long it forgot it was one.
Primary discipline: Shaping (forceful geological manipulation, terrain destruction, volcanic power, seismic events).
Combat identity: Aggressive overwhelming force. Highest direct damage, terrain destruction, volcanic power. Difficult to play defensively.
Player archetype: Aggressive PvP, territorial conquest, direct military confrontation.
Starting zone: The Scorch Plateau.
Visual palette: Deep volcanic black (#1a1208), forge orange (#d4580a), ash grey (#6b6359), blood-oxide red (#8b1a0f), obsidian sheen (#2d2520).
UI tone: Theocratic severity — geometric and heavy, minimal ornamentation except militaristic heraldry, weight and permanence.

THE DEEPWALKERS:
Territory: No single surface territory. Underground karst networks beneath much of the settled Dern. Bioluminescent cave systems of cathedral scale.
Cultural identity: The oldest continuous civilization in the Dern. The Fracturing barely touched them underground. An elder Deepwalker considers a 200-year project a medium-term initiative. They are ancient, methodical, and deliberately opaque. They have records and cultural memory no surface civilization can match. They resist any faction threatening to use Founder technology in ways that destabilize underground geology.
Architecture: Organic, shaped over generations following material logic. Cathedral-scale karst chambers. Natural formations are never destroyed — only shaped incrementally. Surface presence is intentionally minimal.
Primary discipline: Resonance (understanding and manipulation of geological resonance, the deep language of the Dern, and the operating language of Founder technology — the ancient civilization that once stabilized the world's geology).
Combat identity: Patience and attrition. Cave-fighting specialists: darkness manipulation, sound-based disorientation, collapse trap mechanics. Very powerful underground; weaker on open surfaces.
Player archetype: Lore depth, scholarly pursuits, underground exploration, moral complexity. The deepest access to Founder technology and ancient history.
Starting zone: The Deepwalker Karst.
Visual palette: Deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f), pale limestone (#d4cdb8), deep water blue (#0a1a2a).
UI tone: Ancient, patient, scholarly. Information as if carved into stone. Reveals slowly. Deep time aesthetic.

THE TIDE COMPACT:
Territory: The Shatter Coast and the archipelago of new islands created by the Fracturing. Storm coasts, drowned ruins visible through shallow water, new volcanic islands still smoking from recent uplift.
Cultural identity: Young civilization (300 years), diverse in ethnic origin, unified by maritime culture and necessity. A confederation of Fracturing-displaced survivors who built something new from the wreckage. Status is determined by what you have found, built, or mapped — pure meritocracy. The most forward-looking civilization in the Dern.
Architecture: Modular, designed to be disassembled, weather-battered and practical. Built to relocate because the Compact learned that attachment to specific geography is a liability.
Primary discipline: Charting (geographical mastery, exploration, documenting and claiming new territory, first-mover advantages).
Combat identity: Speed and adaptability. Flanking, weather exploitation, controlled withdrawal. Cannot hold ground well but excellent at selecting fights they can win.
Player archetype: Exploration, discovery, maritime gameplay, first-mover territorial advantage, procedurally generated frontier access.
Starting zone: The Shatter Coast.
Visual palette: Storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a), sea-glass green (#5a9e8a), weathered off-white (#d4cdb8), deep ocean (#0a1a2a).
UI tone: Meritocratic and forward-looking. Clean, practical, slightly rough edges. Nautical chart aesthetic for maps and data.

THE GEOLOGICAL DISCIPLINE SYSTEM:
Players choose a primary discipline at character creation. The four disciplines are:
- Reading (Varekian): geological intelligence, resource forecasting, trade route optimization.
- Shaping (Ashbound): forceful terrain alteration, volcanic power, mine development.
- Resonance (Deepwalkers): geological resonance, Founder technology interface, rare material identification.
- Charting (Tide Compact): exploration mastery, first-finder bonuses, frontier territory access.
Players can cross-train in secondary disciplines over time. Cross-training is meaningful — a Reading practitioner with secondary Resonance is a distinct archetype with real advantages, not just more of the same.
Progression is measured in Strata depth: Surface Understanding (1–10), Formation Understanding (11–25), Mantle Understanding (26–40), Core Understanding (41–50).

THE FRACTURING:
400 years ago, an ancient civilization called the Founders disappeared. The Founders maintained a planetary-scale geological suppression system called the Anchor Network. When they collapsed, 800 years of accumulated tectonic pressure released over 40 years. The single continent cracked. Mountains rose and fell. The current world — with its fractured geography, separated civilizations, and ongoing geological instability — is the result. The Fracturing is not over: the world is still settling.

DESIGN SURFACE:
The character creation / faction selection screen — a full-screen menu that is the player's first consequential choice before entering the world. The screen must communicate that these are real civilizations with real trade-offs, not cosmetic skins.

FUNCTIONAL REQUIREMENTS:
1. Screen layout: four faction panels arranged in a 2×2 grid or a horizontal four-column layout. Each faction occupies its own visual zone with its own palette and architectural motif. The contrast between factions should be stark and meaningful.
2. The VAREKIAN COMPACT panel is in "selected" state for this mockup. Show it as expanded/highlighted. Other panels are in the "unselected but visible" state — enough information to compare, less visual prominence.
3. Each faction panel (unselected) must show:
   - Faction name (large)
   - Territory/homeland (one line)
   - Primary discipline (one line)
   - Two-sentence cultural identity summary
   - One-sentence combat identity
   - "Recommended for:" player archetype note (one line)
4. Selected Varekian Compact panel additionally shows:
   - Discipline description (Reading — 2–3 sentences)
   - Starting zone name: "The Varek Delta"
   - A hint of territory geography (a subtle horizontal platform-city silhouette, not a detailed map)
   - Expanded cultural detail
5. Screen header text (not "Choose Your Class"): "Which people are yours?" — in a typographic treatment appropriate to the game's geological tone.
6. A character name input field, shown in the selected faction's visual style.
7. A confirmation action — styled as a document or contract signing, not a game menu button. Text: "Enter the Dern as a child of the Varekian Compact." With a secondary note: "This choice is consequential — it shapes your starting world, your discipline, and your faction's memory of you."
8. A small "Begin unaffiliated" link/option below the confirmation — for players who want to defer faction choice. Style this as clearly secondary, not recommended, but available.
9. The screen background should show geological strata connecting all four panels — deep stone layers at the base, implying all four civilizations exist on the same geological foundation.

VISUAL CONSTRAINTS:
VAREKIAN COMPACT (selected state): Panel background tidal grey-green (#7a9e8e), text on aged brass (#b5894f) panels, salt-flat white (#e8e4d9) body text, deep river brown (#3d2b1f) deep panel fills, verdigris (#5a8a7a) accents. Architectural motif: horizontal platform-city forms, timber frames, brass hardware detail.
THE ASHBOUND (unselected): Panel background deep volcanic black (#1a1208), forge orange (#d4580a) accent borders and faction name, ash grey (#6b6359) body text, blood-oxide red (#8b1a0f) on threat/combat indicators. Architectural motif: vertically imposing carved rock forms, obsidian sheen.
THE DEEPWALKERS (unselected): Panel background deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity) on organic cave forms, mineral amber (#c49a2f) accents and faction name, pale limestone (#d4cdb8) body text. Motif: organic karst forms, bioluminescent vein lines. This panel reveals slowly — not immediately loud.
THE TIDE COMPACT (unselected): Panel background deep ocean (#0a1a2a), storm grey-blue (#4a6b7a) on structural elements, salvage rust-orange (#c4622a) on faction name and active accents, weathered off-white (#d4cdb8) body text. Motif: modular nautical construction, chart-line geometry.
Background geological strata connecting all four panels: dark slate (#1a1a1a to #2a2520) with subtle geological layer lines visible.
Tone: Weight and permanence. This is the most consequential choice of the player's early game. The screen communicates real civilizational difference, not cosmetic variety. No faction should look objectively better or worse — each should look like it costs something to choose.
Anti-patterns: No "recommended" badges implying one faction is easier. No power/level rating. No fantasy race (species) selection language. No generic game menu visual language (these panels should feel like windows into actual places, not UI cards). No glowing arcane effects. No floating UI elements without architectural grounding.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific faction and discipline data given above (not "Lorem ipsum")
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-004-character-creation-faction-select.html`
