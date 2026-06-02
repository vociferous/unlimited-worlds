# REQ-009 — Resource Node Depletion Overlay (In-World Display)

**Domain:** UI/HUD
**GDD Reference:** Section 5.1 (Gathering — node depletion, first-finder bonus, Common Ground, extraction methods), Section 2.3 (Phase 3: Mark — resource extraction → node depletion marker), Section 6.2 (Claim Stakes)
**Phase Relevance:** Phase 2
**Source Session:** Mechanic Designer Session 001 (Question 5: Economy — Gathering Subsystem), GDD-v0.1 Section 5.1
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

1. An in-world contextual overlay that appears when the player approaches a resource node. Shows the node's current state without taking the player out of the world — this is a HUD overlay anchored to the node in the game world, not a UI panel that replaces the view.
2. Yield percentage: current remaining yield shown clearly. The node has been partially extracted by previous players — show it at approximately 60% depleted (40% remaining). The depletion is visible both in the UI overlay and suggested in the node's visual appearance.
3. First-finder attribution marker: the first player to discover this node gets a permanent minor yield bonus and their discovery is attributed. Show the attribution — a small marker with a player name ("KAEL DURST — First Survey") and the discovery date.
4. Claim Stake flag: this node has an active Claim Stake. Show the stake holder (player name: "MIRA ASHVEN — Compact Claim"), the time remaining on the stake (38h 14m), and the extraction priority implication ("Priority extraction: stake holder only. Standard access: others at reduced yield.").
5. Extraction method selector: show the three extraction methods — Blast (fast/moderate yield/terrain damage), Precision (slow/high yield/terrain preserved), Standard (medium/medium/neutral) — with the player's current access displayed. For this mockup, the player has Reading Formation depth: Precision requires Resonance Formation, so it is locked; Blast requires Shaping Formation, locked. Standard is accessible. Show the locked methods with their requirements.
6. Geological node data: show the node's geological classification, origin formation type, and any special material properties. This is the information a Reading discipline player gets from surveying.
7. The overlay should not block the view of the node itself — it should frame or annotate the node, not replace it.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact (default player faction). The overlay is a HUD element that anchors to the in-world node position.

**Color guidance:** Tidal grey-green (#7a9e8e) overlay panel, aged brass (#b5894f) yield indicator borders, salt-flat white (#e8e4d9) text, deep river brown (#3d2b1f) panel backgrounds. Yield percentage as a geological depth gauge (not a health bar) — amber (#c49a2f) fill showing remaining yield, depleted portion in muted grey.

**Claim Stake visual:** The stake flag in the world should be visible as a physical object — a marked stake with a Varekian Compact flag. The UI overlay shows the stake's administrative details.

**Depletion visual language:** The node itself (represented in the mockup background) should show visible signs of extraction — material removed from the surface, tool marks, partial excavation. The yield percentage echoes this visual depletion.

**Tone:** A geological survey readout combined with a trade ledger entry. Practical, information-dense, grounded. Reading the node's state should feel like reading a geological instrument.

**Anti-patterns:**
- No glowing resource node (no magical glow emanating from the ore)
- No health-bar-style red/green yield indicator — geological depth gauge aesthetic only
- No generic MMO "click to harvest" tooltip style
- No floating text without material grounding

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath, a world of geological fantasy. Resources are not respawning nodes — they are geological formations that require geological knowledge to extract efficiently. Nodes are finite, depletable, and carry persistent marks of who found and extracted from them.

THE GATHERING SYSTEM:
- All resource nodes have finite yield. Depletion is visible to other players. Regeneration rate scales with local geological activity.
- SURVEY (Reading discipline): before extracting, a skilled player surveys the formation to predict quality, yield, structural risk, and geological characteristics. Players without Reading discipline extract without this information.
- EXTRACTION METHODS: (1) Blast Extraction (Shaping Formation depth required) — fast, moderate yield, damages surrounding terrain, reduces total node yield; (2) Precision Extraction (Resonance Formation depth required) — slow, high yield, preserves terrain, maximizes node yield; (3) Standard Extraction (no special discipline) — medium speed, standard yield, neutral terrain effect.
- FIRST-FINDER BONUS: the first player to discover and document a resource node receives a permanent minor yield bonus on that node, recorded in their Geological Legacy and visible to other players as a discovery attribution marker.
- COMMON GROUND GUARANTEE: designated Common Ground areas in every zone have nodes that regenerate daily. Higher-yield deep-field nodes require more discipline investment to access.
- CLAIM STAKES: a player or guild can stake a resource area, giving extraction priority to the stake holder. Other players can still extract at reduced yield. Automated extraction is blocked for non-holders. Stakes last 72 hours; require renewal.

THE VAREKIAN COMPACT visual identity for this interface:
Materials: aged timber, polished river stone, brass fittings, salt crystal accents.
Palette: tidal grey-green (#7a9e8e) panel backgrounds, aged brass (#b5894f) borders and active indicators, salt-flat white (#e8e4d9) primary text, deep river brown (#3d2b1f) dark fill, verdigris (#5a8a7a) secondary highlights, mineral amber (#c49a2f) for yield/discovery indicators.
Tone: geological survey readout combined with a trade ledger entry. Information-dense, tabular, annotated. Nothing decorative that is not functional.

DESIGN SURFACE:
The resource node depletion overlay — a contextual HUD overlay that appears when a player approaches a resource node in the world. The player is a Varekian Compact Reading practitioner at Strata 17 (Formation Understanding). They have just surveyed this node using their Reading discipline and are viewing its current state.

The resource node for this mockup: a SALT CRYSTAL FORMATION in the Eastern Salt Flat sub-zone of the Varek Delta. The node has been partially extracted by previous players.

FUNCTIONAL REQUIREMENTS:
1. Scene composition: show the overlay anchored to a salt crystal formation node. The node itself should be represented as a CSS illustration in the background — a cluster of pale white/grey mineral crystal columns rising from a salt flat surface, with visible extraction marks (some crystals partially removed, tool scoring visible on surfaces). The overlay panels are positioned around the node, not covering it.
2. YIELD INDICATOR — prominent:
   Node name: "Eastern Salt Crystal Formation — Node ESF-7"
   Classification: "Geological class: Tidal boundary crystallization / Formation type: Evaporite column cluster"
   Yield remaining: 40% (60% depleted). Show this as a geological depth gauge — a vertical column fill from bottom, labeled in geological terms ("40% yield remaining — estimated 23 units recoverable"). The depleted portion should be visually distinct (exhausted/grey) vs. remaining (mineral amber #c49a2f fill).
   Regeneration forecast: "Geological recovery: ~18 days at current tectonic activity. Tidal activity is low — recovery slow."
3. FIRST-FINDER ATTRIBUTION:
   Small attribution marker: "First Surveyed: KAEL DURST — 8th Tide-Turn, Year 423 PF"
   A small brass pin visual — the attribution feels physically tacked to the node record.
   Note: "First-finder yield bonus active for stake holder: +8% on precision extraction."
4. CLAIM STAKE STATUS — clearly marked:
   Stake holder: "MIRA ASHVEN — Varekian Compact Claim"
   Time remaining: "38h 14m until renewal required"
   Extraction priority: "Priority extraction rights: stake holder. Other players: Standard method only, at -30% yield."
   Stake state: ACTIVE / DEFENDED (no warning — stake is within the 12-hour defense window).
   Visual: a small Varekian Compact flag marker visible as part of the node illustration.
5. EXTRACTION METHOD SELECTOR:
   Three methods displayed as a choice panel:
   BLAST EXTRACTION: "Fast / Moderate yield / Terrain damage" — LOCKED: "Requires Shaping Formation depth." Show with Ashbound palette hint on lock indicator (forge orange #d4580a at low opacity).
   PRECISION EXTRACTION: "Slow / High yield / Terrain preserved" — LOCKED: "Requires Resonance Formation depth." Show with Deepwalker palette hint (bioluminescent blue-green at low opacity).
   STANDARD EXTRACTION: "Medium speed / Standard yield / Neutral terrain impact" — AVAILABLE. Highlighted as the accessible option. "Estimated yield at standard method: 18 units (limited by Claim — stake holder priority)."
   "Begin Standard Extraction" action available.
6. SURVEY READOUT (Reading discipline bonus information):
   A panel showing what the Reading discipline survey revealed:
   "Survey conducted — Reading Formation Strata 17:
   Material quality: High purity evaporite (Tier 2 crafting use: Salt-Reinforced Masonry, food preservation, chemical processing)
   Structural risk: Low — column stability adequate for Standard extraction
   Geological note: Tidal boundary formation — indicates fresh/salt water mixing at this location for 10+ years. Consistent with Northern Channel disruption post-Fracturing."
7. Layout: the overlay should be arranged around the node illustration — perhaps a left panel for yield/attribution, right panel for claim/extraction, bottom panel for survey readout. The node is always visible in the center.

VISUAL CONSTRAINTS:
Overlay panels: aged timber frame (#3d2b1f), aged brass borders (#b5894f), tidal grey-green (#7a9e8e) panel backgrounds.
Text: salt-flat white (#e8e4d9) primary, sepia secondary.
Yield gauge: mineral amber (#c49a2f) for remaining yield fill, deep grey (#4a4540) for depleted portion.
Node illustration: salt crystal columns — pale white to mineral grey (#e8e4d9 to #c8c4b8), with visible extraction marks (slightly darker scoring/chisel marks). Base: salt flat white-grey surface.
Claim flag: small, physical — deep river brown (#3d2b1f) stake post, tidal grey-green (#7a9e8e) flag fabric.
Lock indicators: Shaping/Blast lock tinted forge orange (#d4580a, ~20%); Resonance/Precision lock tinted bioluminescent blue-green (#2aff9f, ~15%). These are subtle hints about which faction/discipline unlocks that method.
Tone: geological survey instrument combined with a property rights ledger. Reading this overlay is a skill — players who understand geological notation get more from it.
Anti-patterns: no magical glow on the node, no red/green health-bar yield indicator, no floating tooltip style without material grounding, no generic MMO harvest prompt.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific node data, player names, and geological details given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-009-resource-node-depletion-overlay.html`
