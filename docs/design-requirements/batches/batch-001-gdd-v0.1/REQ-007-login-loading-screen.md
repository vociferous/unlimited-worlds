# REQ-007 — Login / Loading Screen

**Domain:** Menu/Screen
**GDD Reference:** Section 1 (Game Overview — Vision Statement, Core Pillars), Section 7.1 (The Four Civilizations), World Architect Session 001 (Anchor Network, the Fracturing, world identity)
**Phase Relevance:** Phase 1
**Source Session:** World Architect Session 001 (Anchor Network, Founders, four civilizations, geological fantasy identity), GDD-v0.1 Section 1, Section 7.1
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

1. The first visual impression of the game — the login screen seen before the player has chosen a faction or entered the world. Must establish the tone, the scale, and the identity of the game in a single composition.
2. The Anchor Network as the primary visual motif: the Founders' deep-bore installations — geometric structures of engineered precision embedded in geological material. These are the ruins that all four factions seek. They should appear as a background environmental element — partially buried, geological in scale, suggestive of ancient engineered power without being literally explained.
3. Must imply all four faction identities without showing any single faction explicitly. The design should suggest the world contains all four civilizations while being faction-neutral — this is the screen a player sees before choosing. Subtly, geological material from all four biomes should be represented in the composition: volcanic (Ashbound), salt-crystal/water (Varekian), karst/bioluminescent vein (Deepwalker), coastal/sea-worn stone (Tide Compact).
4. The game wordmark "Unlimited Worlds" centered and prominent. The sub-title "Dern Varath" in secondary treatment below.
5. Login form: minimal — username/password fields and a login button. No social login, no "create account" on this screen (those are separate). Styled in a faction-neutral geological aesthetic.
6. A loading state variant: show what the screen looks like during world load (the same composition, but with a loading indicator replacing the login form). The loading indicator should be geological — not a spinning circle, not a progress bar with percentage. Something that conveys slow geological time.
7. A tagline or world description: one line, below the wordmark. Suggested: "A world shaped by what you do in it." or "The world remembers." Keep it short — the visual environment should do the heavy lifting.

---

## Visual Constraints

**Primary visual motif — the Anchor Network:**
The Founders built geological suppression installations — deep-bore machines of ancient engineering now partially buried and ruined. In the login screen, suggest this as: a vast geometric stone structure partially visible behind/through the composition — something that is simultaneously architecture and geology. Geometric precision suggesting engineering, but surfaced with 400 years of geological accretion. This is NOT a glowing magical device. It is a monument to a lost civilization, present in the rock itself.

**Multi-biome geological palette (faction-neutral):**
The composition should contain all four material registers:
- Volcanic/obsidian (Ashbound): deep volcanic black (#1a1208), heat crack orange (#d4580a) at low intensity in deep background
- Salt crystal/water (Varekian): tidal grey-green (#7a9e8e) water or mist, salt-flat white (#e8e4d9) mineral formations
- Bioluminescent karst (Deepwalker): bioluminescent blue-green (#2aff9f at ~15% opacity) as trace vein lines in rock, deep water (#0a1a2a)
- Coastal worn stone (Tide Compact): storm grey-blue (#4a6b7a), salvage rust at very low intensity (#c4622a at ~20%)

**Dominant tone:** Deep stone, deep time. The overall composition should feel like looking at a cross-section of geological history — layers of time visible in the composition. Dark and weighty, but not hostile or oppressive. The darkness is the darkness of deep earth, not the darkness of evil.

**The wordmark:** Centered, prominent. Uses the Direction A or Direction B treatment from REQ-006 (geological gravitas). White or pale limestone (#d4cdb8) letterforms against the dark geological background.

**Loading indicator:** Suggest geological process — slow crystal growth radiating outward, strata lines appearing one by one, a bioluminescent vein slowly illuminating. NOT: a spinning circle, a progress percentage, a loading bar. Something that makes the player feel the world is being assembled from geological time.

**Anti-patterns:**
- No single faction's aesthetic should dominate — this is the pre-faction screen
- No fantasy adventure visual language (no hero silhouettes, no dramatic weapon displays, no fantasy sky)
- No magical glow effects — geological light only (mineral, bioluminescent, heat glow from rock)
- No busy UI — the login form should be minimal and peripheral to the environmental composition
- No neon, no electric blue, no purple void
- No title-screen action-game composition (dramatic angles, motion blur, combat staging)

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern" — meaning "the Old Dark"). The world is a geological fantasy: power comes from understanding deep-earth geological forces, not from divine magic or arcane energy. The world's history is literally buried in geological strata.

THE FRACTURING AND THE ANCHOR NETWORK:
400 years before the game's present, an ancient civilization called the Founders maintained a planetary-scale geological suppression system called the Anchor Network: a series of deep-bore installations that transmitted stabilizing resonance through the planet's crust, holding the single continent stable for 800 years. The Founders' civilization collapsed. The Anchor Network went dark. 800 years of accumulated tectonic pressure released over 40 years. The single continent cracked along dozens of fault lines — mountains rose and fell, shallow seas formed, entire civilizations were displaced. This 40-year catastrophe is called the Fracturing.

The Anchor Network installations are now ruins — partially buried, geologically integrated, spread across the fractured world. All four civilizations seek them for different reasons. Recovering and activating (or deliberately destroying) an Anchor installation is a player-achievable goal with world-scale consequences.

The Anchor Network installations are architectural objects of engineered precision: geometric deep-bore structures built to last millennia, now 400 years into abandonment and geological reclamation. They look like: a circular geometric structure partially sunk into rock, with regular geometric precision (suggesting ancient engineering) but surfaced with geological accretion — mineral deposits, crystal growth along seams, water staining, structural weathering. Geometric precision becoming geological material over 400 years.

FOUR CIVILIZATIONS (subtle presence in the composition — no single faction dominant):
- THE VAREKIAN COMPACT: river delta engineers. Suggest with: tidal grey-green water (#7a9e8e), salt crystal mineral formations (pale #e8e4d9), brass-toned glints.
- THE ASHBOUND: volcanic plateau theocrats. Suggest with: deep volcanic black (#1a1208), low-intensity heat crack orange (#d4580a) deep in the background, obsidian texture.
- THE DEEPWALKERS: ancient underground karst civilization. Suggest with: bioluminescent blue-green vein lines (#2aff9f at very low opacity, ~15%) in rock, deep water blue (#0a1a2a) in shadow, limestone pale (#d4cdb8).
- THE TIDE COMPACT: young coastal confederation. Suggest with: storm grey-blue (#4a6b7a) mist/water, sea-worn stone texture.

UNIVERSAL VISUAL LANGUAGE: geological base — deep stone textures, slate, obsidian, earth tones throughout. Magic/power expressed as: crystal growth, heat glow through rock, bioluminescent veins, slow mineral light. NOT fire, NOT electricity, NOT arcane sparkle. Anti-patterns: generic fantasy chrome/gold filigree, floating arcane runes without geological grounding, purple void magic, neon effects.

DESIGN SURFACE:
The login and loading screen — the first visual impression of the game. Shown in two states:

STATE A: LOGIN SCREEN — the player has not yet logged in. Shows the login form over the environmental composition.
STATE B: LOADING SCREEN — the player has logged in and the world is loading. The login form is replaced by a geological loading indicator.

Show both states in a single document (STATE A at top, STATE B below, or side by side).

FUNCTIONAL REQUIREMENTS:

STATE A — Login Screen:
1. Full environmental composition (see visual description below) occupying the entire viewport.
2. The Anchor Network structure as the central visual element — partially visible in the background, geological and monumental, not glowing or magical.
3. The game wordmark "UNLIMITED WORLDS" centered, large, in a geological typographic treatment (see typography guidance below). Below it, in smaller secondary treatment: "DERN VARATH."
4. A tagline line below the sub-title: "The world remembers." — small, spaced letterforms, restrained.
5. Login form, centered below the wordmark, minimal:
   - Username field: placeholder text "Your name in the Dern"
   - Password field: placeholder text "Your passage key"
   - Login button: text "Enter the Dern" — styled in geological material, not a generic button.
   - The form container should feel like a physical material element — aged stone panel or parchment-on-stone — not a floating glass overlay.
6. No other UI elements. No social login. No "create account" (separate flow). No news headlines.

STATE B — Loading Screen:
1. Same full environmental composition and wordmark.
2. Login form replaced by a loading indicator. The loading indicator must be geological — NOT a spinner, NOT a percentage bar. Suggested: a circle of geometric Anchor Network-style nodes slowly illuminating one by one (8–12 nodes, like activation points on an ancient installation); or a horizontal geological strata line filling left to right with mineral color; or a bioluminescent vein slowly extending across a stone surface. The indicator should feel like the world is being assembled from geological time, not downloaded from a server.
3. Below the loading indicator: a single rotating geological fact or world detail. Use these specific lines in rotation (show one visible):
   - "The Founders maintained the Anchor Network for 800 years. It has been dark for 400."
   - "The Deepwalkers have records of the pre-Fracturing world. They share them selectively."
   - "A Claim Stake lasts 72 hours. An undefended stake lasts 12."
   - "Geological strata accumulate at approximately one millimeter per year. The Fracturing laid down forty meters in forty years."
   - "The world was not made for you. It was here before you arrived."

VISUAL CONSTRAINTS — THE ENVIRONMENTAL COMPOSITION:
The background composition should feel like looking at a geological cross-section or a deep underground space. Key elements:

Central focus: a partially buried Anchor Network installation — an ancient circular geometric structure emerging from rock. It is NOT glowing. It is stone, mineral, aged. Its geometric precision contrasts with the geological material it is embedded in. Mineral deposits have grown along its seams over 400 years. It looks like engineering that has been claimed by geology.

Surrounding the installation: layered geological strata. Multiple layers of rock composition visible — each layer a different tonal value, suggesting depth of time. These layers should subtly hint at the four biomes:
- A volcanic black obsidian layer (Ashbound register) — deep, in the lower sections
- A grey-green layer with mineral crystalline formations (Varekian register) — mid-section
- A limestone pale layer with bioluminescent vein traces in blue-green (Deepwalker register) — upper section, interior of cave
- A sea-worn stone layer with storm blue tones (Tide Compact register) — visible at one edge

Light: no dramatic directional light source. Geological light: very faint bioluminescent blue-green traces (#2aff9f at ~15% opacity) in mineral veins. Very faint heat-glow amber from deep below (volcanic register, very subtle). Pale limestone (#d4cdb8) as the lightest tone in the mid-composition. Overall: dark, but with depth — not a flat black background.

Typography for wordmark "UNLIMITED WORLDS": Use CSS to create stone-carved letterforms. Options: large, widely tracked uppercase with heavy weight (suggesting carved stone); or a geometric serif with text-shadow creating slight relief depth. Color: pale limestone (#d4cdb8) or salt-flat white (#e8e4d9) against the dark background. "DERN VARATH" below in smaller size, more letter-spacing, slightly more translucent — a secondary inscription.

Login form container: a dark stone panel feel — background (#1a1208 to #2d2520), thin aged brass border (#b5894f at 60% opacity), input fields with parchment-tinted backgrounds (#e8e4d9 at 10% opacity) and salt-flat white text. Login button: aged brass-toned with dark text.

Dominant palette: Deep volcanic black (#1a1208) and deep slate (#2d2520) form the primary dark tones. Pale limestone (#d4cdb8) is the lightest element. Mineral amber (#c49a2f) used sparingly for geological accent. Bioluminescent blue-green (#2aff9f at 15% opacity) for trace vein lines only.

Anti-patterns: No single faction dominant. No hero silhouette or character art. No dramatic action-game composition. No magical glow. No electric blue. No purple. No neon. No fantasy gold filigree. No floating elements without material grounding. The composition should feel like a document of a place, not a movie poster.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Show both State A (login) and State B (loading) — either as separate sections or as labeled panels within one page
- Use the specific loading screen text lines given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-007-login-loading-screen.html`
