# REQ-011 — Zone Map Overlay

**Domain:** UI/HUD
**GDD Reference:** Section 2.1 (Phase 1: Read — "Resource field state: visible depletion status, Claim Stake markers"), Section 6.2 (Claim Stakes — "visible world marker… icon on zone map"), Section 7.2 (Historical Ledger — "World map flags on locations associated with Ledger entries"), Section 2.5 (Weekly Loop — geological cycle)
**Phase Relevance:** Phase 2
**Source Session:** Mechanic Designer Session 001 (Read phase, exploration, cartographic updates), GDD-v0.1 Sections 2.1, 6.2, 7.2
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

1. An in-play map panel (opened during play, overlaid on the game world) showing the current zone and surrounding region. The Varek Delta region for this mockup.
2. Zone control indicators: show territorial control state for different sub-zones — Varekian Compact controlled, Tide Compact contested, neutral/unclaimed. Each controlled zone clearly attributed to its faction.
3. Claim Stake markers: visible flags on the map showing active Claim Stakes, their holders, and whether any are in Contention status (contested or approaching the 12-hour undefended threshold).
4. Faction Ledger location flags: map markers on locations associated with recent Historical Ledger entries. Players can see where significant events occurred geographically.
5. Cartographic discovery attribution: areas that have been mapped show attribution (who documented this zone and when). Unmapped territory shows as blank — the edge of known geography. The Tide Compact's cartographic expertise means their maps are more detailed in coastal areas.
6. Tectonic pressure indicator: a zone-level indicator showing current tectonic activity level — calm, mildly active, precursor-event state. The geological simulation is partially visible to players — geological scholars can read it, and the map should show a coarse-grained tectonic state for the region.
7. The map should feel like a cartographer's working document — a nautical chart crossed with a geological survey, not a minimap with icons floating over a rendered terrain image.

---

## Visual Constraints

**Map aesthetic:** Varekian Compact cartographic tradition — a nautical chart aesthetic for water/delta areas, combined with geological survey notation for land areas. Handcrafted-feeling line work. Tide markers, depth soundings, sandbar notation. Geological strata annotations at zone boundaries.

**Faction territory color coding:**
- Varekian Compact: tidal grey-green (#7a9e8e) with aged parchment (#e8e4d9) base
- Tide Compact: storm grey-blue (#4a6b7a)
- Ashbound: forge orange (#d4580a) tint, distant
- Deepwalker: mineral amber (#c49a2f) for underground karst markers
- Neutral: aged parchment base (#e8e4d9) without faction tinting
- Contested: muted overlap of both faction colors, or a specific contested hatch pattern

**Tectonic pressure indicator:** a compass-rose-adjacent element showing geological state — a minimal geological dial or an annotated cross-section showing activity level. "Tectonic state: STABLE" with a mineral-amber indicator for "PRECURSOR — minor tremors reported."

**Tone:** A working document. Annotated by multiple hands over time. Survey marks, depth soundings, geological notes in the margins. The map is not a clean digital interface — it looks like it was made by a person with ink, corrected over time, with new annotations layered over old ones.

**Anti-patterns:**
- No rendered 3D terrain minimap (no World of Warcraft-style floating over 3D terrain)
- No floating icon soup with dozens of quest markers
- No clean vector game-UI aesthetic — this should look like a real cartographic document
- No neon highlighting on territory borders
- No minimap-style rotation locked to player direction

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath, a world of geological fantasy. Geography is politically meaningful: who controls which territory controls economic resources. The world is still recovering from the Fracturing — a geological catastrophe 400 years ago that split the single continent along dozens of fault lines. The world's geography is mutable: tectonic events can alter zone terrain, and player actions can reshape geography.

Four civilizations compete for territory:
- THE VAREKIAN COMPACT: river delta merchants. Territory: Varek Delta. Visual: tidal grey-green (#7a9e8e), aged brass (#b5894f), aged parchment (#e8e4d9). Cartographic tradition: nautical chart aesthetic, depth soundings, tide markers, trade route notation.
- THE ASHBOUND: volcanic plateau theocrats. Territory: Scorch Plateau (distant from this map). Visual: forge orange (#d4580a), ash grey (#6b6359).
- THE DEEPWALKERS: underground karst civilization. Territory: underground, marked on surface maps with amber indicators. Visual: mineral amber (#c49a2f), pale limestone (#d4cdb8).
- THE TIDE COMPACT: coastal confederation. Territory: Shatter Coast and new islands. Visual: storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a). Best cartographers — their maps are more detailed in coastal areas.

KEY MAP SYSTEMS:
HISTORICAL LEDGER LOCATION FLAGS: significant faction events are geographically tagged on maps — players can see where major events occurred. A Ledger flag shows event type (territorial/economic/geological/faction), factions involved, and a brief summary on hover/selection.
CLAIM STAKES: 72-hour temporary extraction priority markers. Visible as physical flags in the world and as icons on the zone map. Stakes in contested zones automatically enter Contention if undefended for 12 consecutive hours.
CARTOGRAPHIC ATTRIBUTION: who documented a zone and when. Unmapped territory is blank — an incentive for exploration. Tide Compact players have coastal detail advantages due to the Charting discipline.
TECTONIC PRESSURE: the world has a simplified geological simulation tracking fault line pressure. Precursor events (tremors, anomalous tides) are observable 7–10 days before a major event fires. The map shows a coarse tectonic state indicator for the region.

THE VAREKIAN COMPACT VISUAL IDENTITY FOR MAPS:
The Compact's cartographic tradition treats maps as working documents: nautical chart aesthetic with depth soundings, tide markers, current arrows, sandbar notation. Geological survey notation at zone boundaries and geological feature markers. Annotations added over time in different hands. The map looks like it was made by cartographers who use it daily, not rendered by a computer.

DESIGN SURFACE:
The zone map overlay — opened during play, overlaying the game world. The map shows the Varek Delta region from above in a cartographic style. The player is a Varekian Compact member currently at the Eastern Dock of Varek's Hold.

FUNCTIONAL REQUIREMENTS:
1. MAP COMPOSITION:
   The Varek Delta region from above, rendered as a cartographic document — parchment base (#e8e4d9), hand-drawn line work, topographic/depth notation. Key geographical features:
   - Varek's Hold: the main Varekian Compact city on raised platforms at the delta center. Marked with Varekian Compact symbol. The player's current position is indicated here.
   - Northern Channel: a river channel to the north, marked with a "BLOCKED — Sandbar shift, Day 3" annotation (active Ledger event visible on map).
   - Eastern Salt Flat: a broad flat area east of the city with salt crystal formation markers (small crystal symbols). Partially contested.
   - Reed Bed Passages: marked waterways through reed marshes, labeled with survey attribution.
   - River tributaries flowing into the delta from the north and west.
   - Shatter Coast visible at the eastern/southern edge (storm grey-blue tint, Tide Compact territory beginning).
   - The deep delta water channels shown with depth soundings in nautical chart style.
   - An unmapped region at the far eastern edge — blank parchment, labeled "Unsurveyed — Tide Compact reported new sandbar formation."

2. ZONE CONTROL INDICATORS:
   Color-tint territorial control areas directly on the map:
   - Varekian Compact core territory (Varek's Hold, main delta platforms, Western Reed Beds): tidal grey-green (#7a9e8e) tint over the parchment base.
   - Eastern Salt Flat: CONTESTED — show as overlapping Varekian grey-green and Tide Compact storm-blue tint, with a dashed contested border.
   - Shatter Coast approach (far edge): Tide Compact storm grey-blue (#4a6b7a) tint.
   - Underground karst zone markers (three small circular markers below the delta): mineral amber (#c49a2f) with Deepwalker notation ("DEEPWALKER KARST — BELOW").

3. CLAIM STAKE MARKERS (on map):
   Three active Claim Stakes shown as small flag icons:
   - Eastern Salt Crystal Formation — Node ESF-7: "MIRA ASHVEN — Active, 38h remaining" — Varekian Compact flag icon.
   - Northern Reed Bed, Survey Point 3: "UNDEFENDED — [COMPACT CLAIM] — Warning: 9h elapsed of 12h defense window" — shown with amber warning color.
   - Eastern approach (contested area): "DOVEN SALT CO. — Disputed — Contention Event pending" — shown with contested marker.

4. FACTION LEDGER LOCATION FLAGS:
   Four map flags referencing recent Ledger entries:
   - Northern Channel (star-type marker): "LEDGER — Economic: Sandbar blockage confirmed, Day 3. Merchant transit delayed."
   - Eastern Salt Flat (flag marker): "LEDGER — Territorial: Varekian Compact vs. Tide Compact stake dispute. Claim registered."
   - Platform District 4 (marker at city center): "LEDGER — Geological: Deepwalker survey — subsurface cavity dispute. Review pending."
   - Reed Bed Western Passage (marker): "LEDGER — Territorial: Reed bed passage rights registered. Attributed: KAEL DURST."

5. CARTOGRAPHIC ATTRIBUTION STRIP:
   In map margins: "Primary survey: Varekian Compact Survey Division, Year 420–423 PF. Eastern approach addendum: Tide Compact Chart Registry, Year 422 PF. Unsurveyed regions: documented as of 14th Tide-Turn, Year 423 PF."
   A small attribution plaque on one corner: "Zone 4: Varek Delta Eastern Sectors — Surveyed and maintained by [player name shown]: KAEL DURST — Discovery credit: ESF-7, Reed Passage West."

6. TECTONIC PRESSURE INDICATOR:
   A compass-rose adjacent element in one corner. Show: a minimal geological dial with three states. Current state: "TECTONIC: STABLE — No active precursors." Show the dial as a circular geological depth indicator, labeled with simple geological notation. A note: "Last tectonic event: Northern Channel sandbar shift, Year 423 PF, Day 12."

7. MAP PANEL FRAME:
   The map panel has a physical frame in Varekian Compact aesthetic — aged timber border (#3d2b1f), brass corner brackets (#b5894f), a map title plaque at top: "VAREKIAN COMPACT SURVEY — VAREK DELTA REGION — Zone 4 Eastern Sectors." Panel includes a compass rose in the corner using Varekian cartographic style (not a fantasy compass).

VISUAL CONSTRAINTS:
Map base: aged parchment (#e8e4d9), slightly off-white with subtle texture suggestion.
Line work: dark sepia (#5a3a1a) for land outlines, river lines, and cartographic notation. Lighter sepia for depth soundings.
Territorial tints: semi-transparent color washes over the parchment — Varekian grey-green (#7a9e8e at 25% opacity), Tide Compact storm-blue (#4a6b7a at 20% opacity), contested areas overlap.
Ledger flags: brass-tack-styled map pins with small annotation cards.
Claim Stake icons: small flag shapes — Varekian Compact colors (#7a9e8e flag, #3d2b1f post). Warning state: mineral amber (#c49a2f) flag.
Tectonic indicator: mineral amber (#c49a2f) for precursor state; verdigris (#5a8a7a) for stable.
Unmapped territory: clean parchment (#e8e4d9) with "Unsurveyed" notation — no terrain detail.
Tone: a working cartographic document. Annotated in multiple hands over time. Not a clean game UI map — a real map made by real surveyors in an ongoing world.
Anti-patterns: no rendered 3D terrain minimap, no floating icon soup, no clean vector game UI aesthetic, no neon borders, no generic fantasy map style (no dragon illustrations, no compass rose with fantasy symbols).

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific location names, player names, and world-state data given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-011-zone-map-overlay.html`
