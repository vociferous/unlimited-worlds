# REQ-014 — Deepwalker Karst Underground HUD Variant

**Domain:** UI/HUD
**GDD Reference:** Section 4.2 (Terrain Stance System — Deepwalker Deep Sense), Section 7.1 (The Deepwalkers — architecture, cultural identity, underground territory), Section 3.1 (Resonance discipline)
**Phase Relevance:** Phase 3+
**Source Session:** World Architect Session 001 (Deepwalker Karst biome, bioluminescent cave systems, underground civilization), Mechanic Designer Session 001 (Deepwalker combat identity — patience and attrition, Deep Sense stance), GDD-v0.1 Sections 4.2 and 7.1
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

1. How the core game HUD (same functional elements as REQ-001) adapts when a player enters underground Deepwalker Karst zones — dramatically different lighting, navigation challenges, and the Deepwalker Deep Sense stance as the available combat modifier.
2. Low-light HUD adaptation: in underground zones, the HUD elements must be legible without overwhelming the bioluminescent low-light environment. The HUD should feel integrated into the cave's visual register — using the Deepwalker visual language, not the Varekian Compact default.
3. Deep Sense stance audio-positional indicator: the Deep Sense stance gives Deepwalker-aligned players sound-based positioning awareness — audio cues indicate enemy movement before visual contact. The HUD must show a spatial audio indicator that represents nearby sound sources as positional data (a minimal radar-like circle showing directional sound events without being a traditional radar). This is a geological sonar concept — sound waves through rock, not electronic radar.
4. Environmental depth indicator: underground, "depth" is a literal and mechanical concept — how deep below the surface is the player? This affects what geological features are accessible and what Deepwalker content becomes available. Show a depth-below-surface indicator.
5. Bioluminescence zone indicator: the cave's bioluminescent fungal growth patterns affect visibility and Deepwalker combat stance effectiveness. Show a zone bioluminescence level indicator.
6. Show a side-by-side comparison of how REQ-001's HUD elements (Varekian Compact default) transform into the underground Deepwalker variant — the same information, presented through a completely different faction's visual language.

---

## Visual Constraints

**Faction aesthetic:** Deepwalker. This is the starkest visual departure from the default Varekian HUD. Materials: shaped karst limestone, bioluminescent mineral veins, ancient polished bone, cave crystal formations. The HUD elements in underground zones should feel as if they are carved from cave material and illuminated by bioluminescent mineral light.

**Color guidance:**
- Deep cave black: #0d0f0e (dominant background)
- Bioluminescent blue-green: #2aff9f at approximately 15–20% opacity for ambient vein effects; higher opacity (40–60%) for active elements
- Mineral amber: #c49a2f for geological data indicators
- Pale limestone: #d4cdb8 for text on dark cave backgrounds
- Deep water blue: #0a1a2a for deep shadow zones

**HUD light discipline:** In underground zones, the HUD must not produce any bright white light that would destroy the cave atmosphere. Maximum brightness should be the bioluminescent blue-green at ~50% opacity on active elements. All other elements are dim or off-state. The cave environment is the primary visual; the HUD is subordinate to it.

**Deep Sense indicator:** A circular audio-positional display. NOT a radar circle with dots. It should look like: a concentric circle of geological material (limestone ring) with ripple patterns showing sound propagation through rock. Directional indicators shown as material disturbance patterns radiating from detected sound sources, not geometric arrows.

**Tone:** Ancient, patient, sensory. The Deepwalkers navigate by listening to the rock. Their HUD in cave environments is less visual and more geological-sensory in character. It conveys depth, patience, and environmental attunement — not speed or aggression.

**Anti-patterns:**
- No bright white or standard white HUD elements
- No generic night-vision green glow
- No electronic radar aesthetic for the Deep Sense indicator
- No neon effects
- The bioluminescent glow should look organic and mineral, not electric

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world of geological fantasy. The game has a default HUD skin for each faction. When players enter radically different geological environments, the HUD adapts to the environmental visual register — same information, expressed through the environment's aesthetic language.

THE DEEPWALKERS — faction identity:
The oldest continuous civilization in the Dern. The Fracturing (400 years ago) barely touched them underground. An elder Deepwalker considers a 200-year project a medium-term initiative.
Territory: underground karst networks beneath much of the settled Dern. Bioluminescent cave systems of cathedral scale.
Cultural identity: ancient, methodical, deliberately opaque. Ancient, patient, scholarly. They resist any faction threatening to destabilize underground geology.
Architecture: organic, shaped over generations following material logic. Cathedral-scale karst chambers. Natural formations are never destroyed — only shaped incrementally. Surface presence intentionally minimal.
Primary discipline: Resonance (understanding and manipulation of geological resonance — the deep language of the Dern and the operating language of Founder technology).
Combat identity: patience and attrition. Cave-fighting specialists — darkness manipulation, sound-based disorientation, collapse trap mechanics. Very powerful underground; weaker on open surfaces.
Visual materials: shaped karst limestone, bioluminescent mineral veins, ancient polished bone, cave crystal formations.
Palette: deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at low opacity ~15–20% for ambient, higher for active), mineral amber (#c49a2f), pale limestone (#d4cdb8), deep water blue (#0a1a2a).
UI tone: ancient, patient, scholarly. Information as if carved into stone. Reveals slowly. Deep time aesthetic.

THE DEEPWALKER KARST BIOME:
A region of surface-level karst terrain — sinkholes, disappearing rivers, cave entrances. Traversal requires vertical thinking; the most valuable resources are underground. Atmosphere: pale forests growing from nutrient-rich cave runoff, bioluminescent fungi near cave mouths, near-silence broken by underground water movement. Underground: cathedral-scale karst chambers, bioluminescent mineral vein networks in the rock walls, ancient polished bone-white formations, underground lakes in deep water blue.

THE DEEPWALKER DEEP SENSE TERRAIN STANCE:
Activates underground or in cave-adjacent environments.
Grants: darkness exploitation (reduced enemy detection range for Deepwalker-side in low-light zones); sound-based positioning awareness (audio cues indicate enemy movement before visual contact); collapse trap mechanic (triggering ceiling instability in geologically weak sections).
Costs: weaker in open-air environments; collapse traps slow to set up and require Resonance depth.
Requires: Formation Understanding in Resonance discipline.
The Deep Sense stance represents the player learning to navigate and fight by geological sound — sound moving through rock, water dripping as a sonar system, the vibration of footsteps through karst limestone.

THE VAREKIAN DEFAULT HUD ELEMENTS (from REQ-001 context — same information, different aesthetic):
1. Geological State Indicator: current zone name, geological classification, activity level.
2. Active Terrain Stance Display: current stance and available stances for terrain.
3. Strata Depth Display: discipline and current Strata tier with progress indicator.
4. Faction Ledger Notification Badge: unread Ledger entries count and preview.
5. Claim Stake Timer: if active, countdown and location.
6. Resource Inventory Strip: compact resource counts.

The Varekian default HUD uses: aged timber frames, brass borders, salt-flat white text, tidal grey-green backgrounds — a mercantile-ledger aesthetic.

DESIGN SURFACE:
Show two HUD states side by side as a design comparison exploration:
SIDE A: The default Varekian Compact HUD (as a reference — a simplified version showing the visual language of the default).
SIDE B: The same HUD elements transformed for a player in an underground Deepwalker Karst zone — same information, same layout logic, but expressed through the Deepwalker visual language and adapted for the low-light cave environment.

Additionally, show the DEEP SENSE STANCE INDICATOR as a third panel below — specific to the underground zone, showing the sound-based positional awareness display.

FUNCTIONAL REQUIREMENTS:

SIDE A — VAREKIAN DEFAULT HUD (reference panel):
Show a simplified version of the Varekian Compact HUD using: aged timber frames (#3d2b1f), aged brass borders (#b5894f), tidal grey-green (#7a9e8e) backgrounds, salt-flat white (#e8e4d9) text. Label this: "Surface / Default — Varekian Compact Skin."
Show the six HUD elements in their Varekian aesthetic as labeled blocks. Not fully detailed — just enough to communicate the visual register.

SIDE B — DEEPWALKER KARST HUD VARIANT:
Same six HUD elements, same spatial layout, but in Deepwalker visual language for underground zones.
Background: deep cave black (#0d0f0e). All HUD panels are carved from cave material — not timber frames, but limestone edge-carved panels, with bioluminescent vein lines (#2aff9f at ~15–20% opacity) running along the edges as the only light source in the panel borders.
Text: pale limestone (#d4cdb8) on deep cave backgrounds. NOT white — pale warm limestone.
Active elements: bioluminescent blue-green (#2aff9f at 40–50% opacity) glow on active state indicators — a mineral organic glow, not an LED glow.
Specific element adaptations:
  1. GEOLOGICAL STATE INDICATOR (underground):
     "Deepwalker Karst — Chamber 7-C: Lower Cathedral Level — Tectonic: Stable"
     Bioluminescent activity: "HIGH — Fungal bloom detected in adjacent chamber. Visibility enhanced."
     Depth below surface: "312 meters — Resonance access: Mantle-depth formations in proximity."
  2. ACTIVE TERRAIN STANCE (DEEP SENSE active):
     "DEEP SENSE — ACTIVE" in bioluminescent blue-green at higher opacity.
     Benefit display: "Darkness exploitation active / Sound positioning: ON / Collapse trap: available."
     Cost reminder: "Open surface: reduced effectiveness."
  3. STRATA DEPTH: same depth indicator but carved-into-stone aesthetic — not a progress bar but a geological depth column indicator showing "Resonance — Formation Understanding — Strata 19" as carved notation.
  4. FACTION LEDGER BADGE: "2 new entries" but styled as a geological parchment — aged, as if the notification is delivered by slow courier from the surface.
  5. CLAIM STAKE TIMER (if active): same functional content, but styled as a carved stone marker rather than a flag timer.
  6. RESOURCE INVENTORY: show Deepwalker-relevant resources — Cave Crystal × 3, Rare Karst Mineral × 1, Bioluminescent Compound × 2, Polished Bone × 4. Same strip layout but with mineral amber (#c49a2f) inventory badge colors.

DEEP SENSE POSITIONAL INDICATOR (third panel):
This is the audio-positional awareness display specific to the Deep Sense stance — it shows nearby sound sources detected through geological sonar.
Layout: a circular display, approximately 200–250px diameter. NOT a radar circle with dots.
Visual concept: the outer ring is polished limestone or cave stone. Inside the ring, concentric circles suggest sound wave propagation through rock — the rings are subtle, not bright. When a sound source is detected, the rings show a gentle ripple pattern on the side of the circle facing the sound source. Sound sources shown as subtle mineral amber (#c49a2f) disturbance patterns in the ring geometry — NOT as colored dots.
Three sound events shown in this mockup:
  - Forward-left (roughly 10 o'clock position): "MOVEMENT — Stone surface, estimated 2 entities, approaching." The ripple pattern is slightly stronger on the forward-left portion of the ring.
  - Below (6 o'clock, slight): "WATER FLOW — Underground stream, consistent." Constant low ripple at bottom of ring.
  - Right (3 o'clock): "IMPACT — Single stone displacement, non-organic." Subtle single ripple on right side.
Below the circle: "Deep Sense — Geological sonar range: 40m / Collapse-point detected: 3 marked."
The indicator panel itself should be carved-cave material with bioluminescent vein lines framing it.

VISUAL CONSTRAINTS:
Deep cave black (#0d0f0e) as the dominant background.
Bioluminescent blue-green (#2aff9f): ambient vein lines at 15–20% opacity; active state elements at 40–50% opacity; maximum on active confirmations at ~60%.
Mineral amber (#c49a2f): geological data, discovery markers, inventory counts.
Pale limestone (#d4cdb8): primary readable text.
Deep water (#0a1a2a): deep shadow zones in panels.
HUD light discipline: NO bright white light. Maximum brightness is bioluminescent blue-green at 60%. The cave environment is always visible through and around the HUD. The HUD is a minimal presence in the cave, not a bright overlay.
Deep Sense indicator: organic/geological NOT electronic. Concentric stone rings, not clean circles. Ripple patterns suggesting sound propagation through rock, not radar sweeps. Mineral amber disturbances, not dots.
Tone: ancient, sensory, patient. The Deepwalker HUD communicates through geological feel — weight, depth, slow light — not through speed or bright signals.
Anti-patterns: no bright white HUD elements, no generic night-vision green, no electronic radar aesthetic, no neon, no glowing magical effects, no bioluminescence that looks like LED light (it must look organic and mineral), no generic dark-mode UI aesthetic.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Show: Side A (Varekian reference), Side B (Deepwalker underground adaptation), and the Deep Sense positional indicator panel
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-014-deepwalker-karst-hud-variant.html`
