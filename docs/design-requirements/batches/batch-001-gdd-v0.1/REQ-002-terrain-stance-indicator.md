# REQ-002 — Terrain Stance Activation Indicator

**Domain:** UI/HUD
**GDD Reference:** Section 4.2 (The Terrain Stance System), Section 4.3 (Large-Scale Combat), Section 4.4 (Edge Cases)
**Phase Relevance:** Phase 1
**Source Session:** Mechanic Designer Session 001 (Terrain Stance System, faction combat identities), GDD-v0.1 Section 4
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

1. Pre-activation state: shows the available Terrain Stances for the current zone's geological terrain type, with activation requirements (faction relationship, minimum Strata depth) for each stance. Stances the player cannot currently use are shown as locked with a reason.
2. Activation channel animation: a 3-second channel animation that communicates the stance is being "read" from the terrain — not a standard progress bar but something geological in character (e.g., stone fissure spreading, crystal forming, tide rising). Must show clearly that the player is channeling and is briefly vulnerable.
3. Active stance display: once channeled, clearly shows the active stance name, its current benefits (as a compact list), and any costs/vulnerabilities that are now in effect. Must be immediately readable mid-combat.
4. Available stances list for current terrain: a compact panel (can be toggled or semi-persistent) showing all stances available in the current zone, their activation requirements, and which are accessible to this player. Players with a different faction's stance available (cross-training) should be distinguishable from their primary faction stance.
5. Stance conflict state: if the zone is undergoing an active geological event, the stance indicator must clearly communicate that stance activation is blocked ("Terrain in flux — stance cannot be held").
6. The indicator must work visually across all four biome types implied by the game: salt flat (Varekian), volcanic obsidian (Ashbound), underground karst (Deepwalker), coastal (Tide Compact). The mockup should show the Varekian Salt Attunement stance as the primary example, with the other stances visible as unavailable options.

---

## Visual Constraints

**Faction aesthetic:** The Terrain Stance indicator is a cross-faction UI element that adapts its visual language to the current terrain. For this mockup, the primary terrain is the Varek Delta salt flat — Varekian Compact aesthetic dominates. The locked stances should subtly show their own faction's visual character to hint at what cross-training unlocks.

**Varekian Compact colors (active/primary):** tidal grey-green (#7a9e8e), aged brass (#b5894f), salt-flat white (#e8e4d9), deep river brown (#3d2b1f), verdigris accent (#5a8a7a).
**Ashbound locked stance hint:** forge orange (#d4580a), ash grey (#6b6359).
**Deepwalker locked stance hint:** bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f).
**Tide Compact locked stance hint:** storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a).

**Channeling animation tone:** The 3-second channel should feel like the player is reading geological information from the ground — something slow, patient, and geological. NOT: a spinning energy vortex, a magic circle, a countdown clock with a digital feel. YES: a salt crystal spreading across a surface, strata lines appearing in the terrain beneath the character, a slow mineral light activating.

**Tone:** The stance indicator is a tactical UI element — readable at a glance during combat, but visually grounded in geology, not in generic fantasy combat UI language. It should feel like reading a geological instrument, not a power-up activation.

**Anti-patterns:**
- No arcane magic visual language (glowing runes, purple/blue energy auras)
- No generic MMO cooldown circle animations
- No floating damage-number-style text
- No neon or electric light effects
- Channel animation must NOT look like a loading spinner

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world whose geology is its metaphysics. The world is a geological fantasy — power comes from understanding geological forces, not divine magic or arcane energy. The world is still recovering from the Fracturing, a 400-year-old event when continental suppression systems failed.

Four civilizations, each with distinct combat and geological identities:
- THE VAREKIAN COMPACT: River delta people. Palette: tidal grey-green (#7a9e8e), aged brass (#b5894f), salt-flat white (#e8e4d9), deep river brown (#3d2b1f), verdigris (#5a8a7a). Combat style: control and redirection, terrain manipulation, crowd control. UI tone: mercantile-ledger, information-dense, tabular, aged document aesthetic.
- THE ASHBOUND: Volcanic plateau people. Palette: deep volcanic black (#1a1208), forge orange (#d4580a), ash grey (#6b6359), blood-oxide red (#8b1a0f). Combat style: aggressive force, terrain destruction, overwhelming damage.
- THE DEEPWALKERS: Underground karst people. Palette: deep cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f), pale limestone (#d4cdb8). Combat style: patience, attrition, darkness and sound manipulation, collapse traps.
- THE TIDE COMPACT: Coastal island confederation. Palette: storm grey-blue (#4a6b7a), salvage rust-orange (#c4622a), sea-glass green (#5a9e8a), weathered off-white (#d4cdb8). Combat style: speed, flanking, weather exploitation, controlled withdrawal.

THE TERRAIN STANCE SYSTEM:
Combat in Unlimited Worlds uses a modified hybrid targeting system layered with a Terrain Stance system. Every biome has a geological state. Players with relevant faction discipline depth can "read" this state and adopt a Terrain Stance — a combat modifier that uses the environment's geological character.

Four Terrain Stances:
1. VAREKIAN SALT ATTUNEMENT (activates on crystalline salt terrain in Varek Delta salt flat sub-zones): Grants crystal fragmentation area-denial when abilities strike formations; high-ground advantage on elevated salt crystals; salt storm trigger if cumulative formation damage exceeds zone threshold. Costs: movement patterns are partially telegraphed (salt crystal terrain makes flanking visible). Requires Formation Understanding in Reading discipline.
2. ASHBOUND VOLCANIC STANCE (activates on obsidian floors in Scorch Plateau and volcanic sub-zones): Grants heat damage rider on physical abilities; access to magma vent eruption triggers. Costs: reduced movement speed; increased vulnerability to cold effects. Requires Formation Understanding in Shaping discipline.
3. DEEPWALKER DEEP SENSE (activates underground or cave-adjacent, Deepwalker Karst sub-zones): Grants darkness exploitation (reduced enemy detection in low-light zones); sound-based positioning awareness (audio cues before visual contact); collapse trap mechanic. Costs: weaker on open surfaces; traps slow to set up. Requires Formation Understanding in Resonance discipline.
4. TIDE COMPACT OPEN WATER STANCE (activates near water in coastal/maritime sub-zones): Grants flanking speed bonus from water-adjacent positions; increased damage during storm events; reduced cast interruption when breaking combat toward water. Costs: only near water; no terrain-denial; weather exploitation requires active storm. Requires Formation Understanding in Charting discipline.

Stance activation requires a 3-second channel. During channeling, the player is briefly more vulnerable to interruption. Only one stance can be active at a time. Switching requires re-channeling. If the zone is in an active geological event (tectonic flux), stance activation is blocked.

Player progression uses Strata depth: Surface Understanding (1–10), Formation Understanding (11–25), Mantle Understanding (26–40), Core Understanding (41–50). Stances require Formation minimum.

DESIGN SURFACE:
The Terrain Stance activation indicator — a composite UI element showing three states:
STATE A: Pre-activation — the available stances panel for a player currently standing on salt crystal terrain in the Varek Delta. The player has Reading discipline at Strata 17 (Formation Understanding). Varekian Salt Attunement is available. The other three stances are locked.
STATE B: Activation channel — the 3-second channel animation playing as the player reads the Salt Attunement stance from the terrain.
STATE C: Active stance — Salt Attunement is active, showing benefits and costs.

Show all three states in a single mockup as a design exploration panel (e.g., three labeled state panels side by side, or as a vertical progression).

FUNCTIONAL REQUIREMENTS:
1. Pre-activation panel (State A):
   - Header: current terrain type ("Eastern Salt Flat — Crystalline Formation Active")
   - Varekian Salt Attunement: shown as available (player qualifies). Show: stance name, two-line benefit summary ("Crystal fragmentation area-denial / Salt storm trigger at threshold"), cost summary ("Movement patterns telegraphed"), activation requirement met ("Formation — Reading ✓"). Include an activation affordance.
   - Ashbound Volcanic Stance: shown as locked. Reason: "Requires Scorch Plateau terrain." Subtle visual uses Ashbound palette (forge orange tint on lock icon).
   - Deepwalker Deep Sense: shown as locked. Reason: "Requires underground or cave terrain." Subtle Deepwalker palette (bioluminescent tint).
   - Tide Compact Open Water Stance: shown as locked. Reason: "Requires coastal water terrain." Subtle Tide Compact palette.
2. Channel animation panel (State B):
   - Show the 3-second channel in progress at approximately 1.5 seconds elapsed (50% through).
   - Visual concept: salt crystal lines are spreading outward from the player's feet position (represent this abstractly — a circular area at the base of the panel with spreading crystal geometry). The channel is NOT a spinning loader or an energy vortex.
   - Show a "CHANNELING — SALT ATTUNEMENT" label with the channel progress indicated by geological means (crystal growth extent, not a percentage bar).
   - Show a vulnerability indicator: "Stance channel — interrupt window active" in a muted warning color.
3. Active stance panel (State C):
   - Large "SALT ATTUNEMENT — ACTIVE" header in Varekian brass/verdigris.
   - Benefits list (compact): "Crystal fragmentation zones active on ability impact" / "Elevated salt formations: +15% positional advantage" / "Salt storm trigger: 0% / 100% threshold" (show a fill bar for the zone threshold — currently empty).
   - Costs reminder (smaller text): "Movement patterns: visible to attentive enemies."
   - Switch/cancel affordance: "Channel new stance (3s)" or "Deactivate."
4. A geological event block state (small inset or footnote panel): show what the indicator looks like when a zone event is active — "TECTONIC FLUX — Terrain stance cannot be held." Style this as a geological warning, not an error dialog.

VISUAL CONSTRAINTS:
Primary faction: Varekian Compact.
Varekian palette: tidal grey-green (#7a9e8e) panel backgrounds, aged brass (#b5894f) borders and active state accents, salt-flat white (#e8e4d9) primary text, deep river brown (#3d2b1f) dark panel fill, verdigris (#5a8a7a) secondary highlights.
Locked Ashbound stance hint: forge orange (#d4580a) on lock/unavailable indicator.
Locked Deepwalker stance hint: bioluminescent blue-green (#2aff9f) at very low opacity on indicator.
Locked Tide Compact stance hint: storm grey-blue (#4a6b7a) on indicator.
Channel animation: geological — salt crystal growth spreading, not energy vortex or digital spinner. Cold mineral light spreading across a surface. Translucent crystalline geometry.
Tone: tactical reading instrument, not power-up activation. Feels like interpreting geological data, not casting a spell.
Anti-patterns: no arcane runes, no glowing energy auras, no generic MMO cooldown circles, no neon effects, no floating orbs, no purple/void color language.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use realistic representative placeholder data as specified above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-002-terrain-stance-indicator.html`
