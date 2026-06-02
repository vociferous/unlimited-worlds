# REQ-006 — Game Logo / Wordmark ("Unlimited Worlds")

**Domain:** Brand/Identity
**GDD Reference:** Section 1 (Game Overview — Vision Statement), World Architect Session 001 (world name decision — "Dern Varath," geological fantasy setting, Anchor Network)
**Phase Relevance:** Phase 1
**Source Session:** World Architect Session 001 (setting identity, geological fantasy decision, world name, Fracturing/Anchor Network), GDD-v0.1 Section 1
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

1. The logotype "Unlimited Worlds" as a wordmark — letter-form treatment is the primary design output. Not an icon-only mark.
2. Must work as a standalone wordmark against a geological/stone backdrop (dark stone texture, obsidian, or deep slate). The game's login screen and loading screen will use it against geological environments.
3. Must also work as a secondary smaller version (for UI corner placement, loading indicators, etc.).
4. An optional accompanying sub-mark or world-title treatment: "Dern Varath" in a secondary typographic style, as the game's in-world name for the world. This appears below "Unlimited Worlds" in formal brand usage.
5. The logotype must communicate: geological gravitas, deep time, civilizational weight, scale. It must NOT communicate: fantasy adventure, magic and sparkles, action-game speed, casual play.
6. Explore at minimum two typographic direction options in the mockup (e.g., a serif direction and a more geometric/carved direction), shown side by side for comparison.
7. The mark should be compositionally strong enough to anchor the login/loading screen (REQ-007) as a centerpiece.

---

## Visual Constraints

**Tone:** Geological gravitas and deep time. The world name "Dern Varath" means "the Old Dark" — a world whose history is literally buried in layers, whose secrets are geological. The logotype must carry that weight. It should feel ancient without being archaic, monumental without being grandiose.

**What this must NOT look like:**
- Generic fantasy adventure (beveled gold letterforms, swooping swords, dragon wings as serifs)
- Action game (sharp angles, speed lines, lens flares)
- Children's fantasy (rounded letters, bright primary colors)
- Sci-fi game (chrome, circuit lines, blue glow)
- Purple/void magic fantasy
- Glowing arcane energy in or around letterforms

**What it SHOULD feel like:**
- Letters carved into or emerging from stone
- Geological strata as typographic structure (layering, depth, weight)
- The gravity of civilizational record — like an inscription on a monument that has been standing for 400 years
- Darkness as depth, not as menace — the "Old Dark" of deep earth, not the darkness of evil
- The Anchor Network as subtle visual motif — geometric precision in the letterforms suggesting engineered structure beneath natural material

**Color guidance:**
- Primary logotype treatment: near-black stone to deep slate (#1a1a1a to #2d2520) for the letterforms themselves
- Geological strata accent: mineral amber (#c49a2f) or pale limestone (#d4cdb8) used sparingly as a highlight or strata line through the letterform
- The wordmark must read clearly against both dark (stone) and light (parchment) backgrounds — show both
- Do NOT use: bright gold filigree, any neon or glow effects, purple or blue magic energy

**Typography direction guidance:**
- Direction A: carved stone serif — letterforms that feel incised or raised from geological material, with weight and permanence
- Direction B: geometric structure — letterforms that suggest the engineered precision of the Anchor Network, with underlying mathematical structure but aged and worn at the surface
- The sub-mark "DERN VARATH" in a smaller, more austere treatment — spaced letterforms or small caps, geological material texture

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern" — "Dern Varath" means "the Old Dark" in the dominant scholarly language). The world is a geological fantasy: its metaphysics are geological, its history is literally buried in stone layers, and its power comes from understanding deep-earth forces rather than divine magic.

The world's central setting concept: the Dern is a world formed from deep-time violence — tectonic collision, volcanic emergence, glacial scour. Its history is recorded in geological strata. Player actions literally accumulate as sediment — ruins, buried cities, fossilized consequences.

The world's central conflict: the Fracturing, a geological catastrophe 400 years ago when the Anchor Network — a civilization-scale planetary geological suppression system built by an ancient people called the Founders — was left unmaintained and failed. The single continent cracked. The world is still settling.

The Founders built the Anchor Network: a series of deep-bore installations that transmitted stabilizing resonance through the planet's crust. These installations are now ruins buried in the world's geography. Whoever recovers and reactivates Founder technology controls the future shape of the world.

Four civilizations now compete over this fractured world:
- THE VAREKIAN COMPACT: river delta merchants and engineers. Palette: aged brass (#b5894f), tidal grey-green (#7a9e8e), deep timber (#3d2b1f). Mercantile-ledger aesthetic.
- THE ASHBOUND: volcanic plateau theocrats who see the Fracturing as divine selection. Palette: volcanic black (#1a1208), forge orange (#d4580a), ash grey (#6b6359). Severity and permanence.
- THE DEEPWALKERS: ancient underground civilization in karst cave systems. Palette: cave black (#0d0f0e), bioluminescent blue-green (#2aff9f at ~20% opacity), mineral amber (#c49a2f). Deep time, patience, scholarly.
- THE TIDE COMPACT: young coastal confederation of Fracturing survivors. Palette: storm grey-blue (#4a6b7a), salvage rust (#c4622a), sea glass (#5a9e8a). Forward-looking, meritocratic.

The game's universal visual language across all factions: geological base — deep stone textures, slate, obsidian, earth tones. Magic/power expressed as crystal growth, heat glow through rock, bioluminescent veins, slow mineral light — NOT fire, NOT electricity, NOT arcane sparkle.

DESIGN SURFACE:
The game logo / wordmark — typographic treatment for "Unlimited Worlds" and an optional companion sub-mark for "Dern Varath" (the in-world name of the game world). This is a brand identity exploration presented as a mockup page showing multiple directions and usage contexts.

FUNCTIONAL REQUIREMENTS:
1. Present TWO typographic direction options for the "Unlimited Worlds" wordmark, side by side or vertically stacked for comparison. Label each direction clearly.

DIRECTION A — "Carved Stone Serif":
Letterforms that feel as if they were incised into or raised from geological material. Heavy serif treatment with visible weight. The letters carry the sense of being cut from stone over a long time — not perfectly rendered, but bearing the marks of geological process. Use CSS to create letter spacing, weight, and treatment that evokes this. Suggest geological layering through the letterforms (perhaps strata lines subtly visible through or beneath the letters).

DIRECTION B — "Anchor Network Geometric":
Letterforms that suggest engineered precision — the geometric logic of the Founders' Anchor Network beneath natural geological material. More structured, with underlying mathematical regularity, but surfaced with geological aging and weathering. The precision of something that was built to last millennia and has.

2. For each direction, show:
   - The full wordmark "UNLIMITED WORLDS" in large treatment against a dark stone background
   - The same wordmark against a light parchment background (reversed usage)
   - A small version at approximately 200px width — the logo at UI scale
   - The companion sub-mark: "DERN VARATH" in a secondary typographic treatment below the main wordmark (smaller, more austere, spaced letterforms or small caps)

3. Show one mockup of the preferred direction in its intended use context: centered on a dark stone background (representing the game's login/loading screen backdrop), with just the wordmark — no other UI elements. This is the "logo in isolation" use case.

4. Provide brief typographic notes below each direction (one line each): what makes this direction appropriate for the game's tone.

VISUAL CONSTRAINTS:
Primary logotype palette: near-black stone (#1a1a1a to #2d2520) for letterform mass, with geological accent used sparingly.
Geological accent options (choose ONE per direction, use sparingly): mineral amber (#c49a2f) — as a thin strata line through the letterform or as a subtle fill; or pale limestone (#d4cdb8) — as a highlight layer suggesting relief carving; or verdigris (#5a8a7a) — suggesting age and oxidation in a geological sense.
Background contexts: dark stone (#1a1208 to #2d2520 range) and aged parchment (#e8e4d9).
Typography implementation: use CSS @font-face with a system serif (Georgia, "Times New Roman", serif) as the base for Direction A. For Direction B, use a geometric sans (system fonts: "Futura", "Century Gothic", Optima, or geometric system fallbacks). Apply CSS letter-spacing, font-weight, text-transform, and CSS text effects (text-shadow, background-clip) to achieve the desired material quality.
Tone: Geological gravitas. Deep time. Civilizational weight. The logo should feel like it was here before the player arrived and will be here after.
Anti-patterns:
- NO generic fantasy gold/silver filigree letterforms
- NO beveled metallic 3D effect (WoW-style logo)
- NO swooping fantasy calligraphy
- NO arcane glow effects (no neon, no blue/purple energy halos)
- NO action game speed design (no italics implying motion, no lightning bolt substitutions)
- NO cartoon roundedness
- The wordmark must NOT look like any existing MMORPG logo — it must look like a geological inscription

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face with web-safe font stacks)
- All content specified above in the functional requirements
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-006-game-logo-wordmark.html`
