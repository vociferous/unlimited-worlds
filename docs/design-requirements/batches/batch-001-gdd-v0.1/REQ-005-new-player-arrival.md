# REQ-005 — New Player Arrival Screen (Varek Delta Barge Approach)

**Domain:** UI/HUD
**GDD Reference:** Section 8.2 (First 30 Minutes: Varek Delta — 0:00–3:00 Arrival), Section 8.1 (Onboarding Principles), Section 8.3 (Starting Zones)
**Phase Relevance:** Phase 1
**Source Session:** Mechanic Designer Session 001 (Question 7: First 30 Minutes, new player experience design principles), GDD-v0.1 Sections 8.1 and 8.2
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

1. The player's first view of the game world: aboard a trade barge approaching Varek's Hold, the main Varekian Compact platform city. The game begins mid-travel — no loading screen, no tutorial overlay, no welcome message.
2. The scene: the barge is on the river approach to the platform city. The city is visible ahead — layered, industrial, already operational. A departing barge passes in the opposite direction, visibly loaded with cargo. Salt crystal formations rise from the shallows on either side of the channel.
3. The primary UI event during minutes 0–3: the NPC ferryman speaks without prompting. His dialogue appears as in-world dialogue (not a tutorial box). It must reference specific, current, local conditions — not a welcome message. Use the GDD-specified opening: something like "Tide's come in high this week. Silt Road merchants been complaining about the north channel again. If you're looking for work, the Factor's post is up the main platform."
4. No tutorial boxes. No onboarding pop-ups. No "press X to continue." The UI during arrival is minimal — the world teaches.
5. Minimal HUD during approach: the player cannot yet interact with the world (they are on the barge); show a minimal UI state — perhaps just the compass/direction indicator and the faction Ledger indicator (showing "Varekian Compact" as the arrival region, with the notice that the Ledger board is visible at the dock). No resource inventory. No Terrain Stance (not yet available to new player).
6. The scene establishes: this world was already in operation before the player arrived. Economic activity is ongoing. The environment contains specific geological details (salt crystals, waterlogged timber, tidal marks) that will later be interactable.
7. The ferryman dialogue display: show how in-world NPC dialogue is presented — NOT a chatbox, NOT a subtitle bar at screen bottom. It should feel like overhearing speech in a physical space, visually grounded in the world. Include a speaker identification (the ferryman's name: "Aldric Vane, River Ferry") but subtly.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact. The arrival scene is the player's first visual encounter with Varekian visual identity as environment, not as UI.

**Environmental color language:**
- River water: tidal grey-green (#7a9e8e) with salt mineral deposits creating pale formations
- Platform city ahead: deep river brown (#3d2b1f) timber structures with aged brass (#b5894f) hardware glints
- Salt crystals in shallows: salt-flat white (#e8e4d9) formations with slight translucence
- Sky: heavy, low — overcast grey suggesting tidal weather; not a bright fantasy dawn
- The barge the player is on: weathered timber decking visible at the bottom of the frame

**Minimal HUD during arrival:**
- Use the same Varekian Compact HUD aesthetic as REQ-001 but in a "minimal/approach" state
- No combat elements active
- No stance indicator (not yet relevant)
- Compass/heading indicator showing: "Approach — Varek's Hold"
- A small notice badge: "Ledger Board — visible at Main Dock"

**Dialogue display tone:** The ferryman's words appear as if spoken into physical space — not a chat window. Consider: floating text with appropriate scale and position near the ferryman's position in the scene; or a minimal speech element grounded in the architectural language of the barge (a weathered wooden plank texture behind the text). The text should feel like ambient world information, not a UI notification.

**Tone:** The world is already in motion. The player has arrived mid-story. The visual language communicates lived-in industrial activity, not fantasy adventure staging. The salt crystal formations should be beautiful in a geological way — not sparkly magic crystals, but real mineral formations that happen to be extraordinary.

**Anti-patterns:**
- No "Welcome to Unlimited Worlds" title cards
- No tutorial boxes, tooltip overlays, or instructional prompts
- No golden sunrise / epic arrival lighting — the Varek Delta is utilitarian and tidal, not dramatic
- No fantasy magic visual language anywhere in the scene
- Do not make the salt crystals look like mana crystals or magical gems — they are geological formations

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world of geological fantasy. The world's metaphysics are geological — power comes from understanding the forces of the earth. The world is recovering from the Fracturing, a geological catastrophe 400 years ago when continental suppression systems failed.

THE VAREKIAN COMPACT — the player's default starting faction:
River delta and lowland basin civilization. Pragmatic merchants and hydraulic engineers who survived the Fracturing by adaptation. Their delta lands flooded rather than cracked. They believe in contracts, information, and knowing the next trade route. Their cities are built on raised timber platforms above the floodplain. Visual identity: aged timber, polished river stone, brass fittings, salt crystal formations from tidal deposits, rope and pulley hardware. Palette: deep river brown timber (#3d2b1f), aged brass hardware (#b5894f), tidal grey-green water (#7a9e8e), salt-flat white parchment/mineral (#e8e4d9), verdigris oxidation (#5a8a7a). Tone: mercantile-ledger — information-dense, tabular, nothing decorative that is not functional.

THE VAREK DELTA — the starting biome:
Flooded river plains with shifting sandbars, dense reed networks, and a disrupted water table from the Fracturing (fresh and salt water now mix in unpredictable layers). Salt crystal formations rise from the shallows where the water table boundary creates crystallization — some are meters tall. The Varekian Compact's major city, Varek's Hold, is built on raised wooden platforms above the floodplain. The city is layered, industrial, complex, and already in full operation.

THE ONBOARDING DESIGN PRINCIPLE:
The game begins mid-travel. There is no loading screen. There are no tutorial boxes. No welcome message. The player arrives in a world that was already in motion before they logged in. NPCs speak about current conditions — not scripted welcomes. Systems teach through interaction, not instruction. The player's first lesson is that this world has ongoing concerns that have nothing to do with them yet.

The Historical Ledger is a public record of significant faction events (territorial changes, economic disruptions, geological events, battles). It is posted on notice boards at town centers. NPCs' dialogue is derived from the current Ledger state. The first NPC the player encounters speaks about something locally and currently specific.

DESIGN SURFACE:
The new player arrival screen — specifically the UI state during the first 0–3 minutes as the player is aboard a trade barge approaching Varek's Hold. This is a screenshot of what the player sees in those first moments: a game world view with minimal HUD overlay, and the ferryman NPC dialogue appearing in-world. There is no tutorial overlay. The scene communicates: you have arrived in the middle of an ongoing world.

FUNCTIONAL REQUIREMENTS:
1. Main visual scene: the player is on a trade barge on the river approach to Varek's Hold. The view is from the deck — looking forward toward the city. Render this as a CSS-illustrated scene (not just a panel — try to compose a scene):
   - The barge deck: weathered brown timber planking in the lower portion of the view, with rope coils and cargo visible.
   - River water on both sides: tidal grey-green (#7a9e8e) water, calm, with reflections.
   - Salt crystal formations in the river shallows: pale white/grey mineral columns rising from the water on both sides of the approach channel. Some are the height of a person. They should look geological — jagged mineral growth, not fantasy gems.
   - A departing cargo barge visible to one side, mid-river, moving in the opposite direction. Laden with crates. The world is already doing business.
   - Varek's Hold ahead: a layered platform city on stilts above the water. Dark timber structures, brass-hardware glints, multiple levels visible. Industrial, complex, operational. Render this as a silhouette or abstract suggestion — enough to communicate scale and character.
   - Sky: overcast, heavy grey — a tidal estuary sky, not a bright fantasy sky.
2. NPC ferryman dialogue: shown in-world, NOT as a chat UI panel. The ferryman stands at the barge's helm (visible in the scene). His dialogue appears near him as if spoken into the physical space — floating text with a minimal aged-parchment backing, not a translucent dialog box. Use this specific dialogue text:
   "Tide's come in high three days running. Silt Road merchants been complaining about the north channel — sandbar's shifted again. Factor Holst posted work at the main platform if you're looking. Mind the crystal field on the starboard approach — tide's been pushing them up."
   Speaker attribution below the text, smaller: "— Aldric Vane, River Ferry, Varekian Compact"
3. Minimal HUD overlay (not the full HUD — arrival mode):
   - Top-left small indicator: Compass/heading — "Approach: Varek's Hold — Northern Dock" with a minimal directional compass rose in Varekian brass style.
   - Top-right small badge: "Ledger Board — visible at Main Dock" — a small parchment-styled badge suggesting the Historical Ledger board awaits at the dock. No count (player has not yet read it). Styled as a small notice pinned to the edge of the screen.
   - No resource inventory (player has no items yet).
   - No Terrain Stance (not yet accessible).
   - No faction affiliation indicator (player has not yet chosen).
   - Everything is minimal — the world is the focus, not the UI.
4. No tutorial elements anywhere. No tooltip overlays. No instructional text. No "Press F to interact" prompts. The only text in the scene is: (a) the ferryman's dialogue, (b) the two minimal HUD indicators, and (c) the speaker attribution. Nothing else.
5. The scene should communicate: this world was operational before the player arrived. Economic activity is visible (the passing cargo barge). The environment contains details that suggest interactability (the salt crystals, the reed beds visible along the bank) without labeling them.

VISUAL CONSTRAINTS:
River water: tidal grey-green (#7a9e8e).
Salt crystals: salt-flat white to pale mineral grey (#e8e4d9 to #c8c4b8). Jagged, geological. NOT sparkly gems or mana crystals.
Barge decking: deep river brown (#3d2b1f) timber with grey weathering.
City silhouette ahead: deep brown (#3d2b1f) with aged brass (#b5894f) glints on hardware. Layered, horizontal, industrial.
Sky: cool grey, overcast (#8a8e8a to #6a7070). Not dramatic. Tidal estuary sky.
Departing barge: same timber palette, darker with distance.
Ferryman dialogue backing: very subtle aged parchment (#e8e4d9 at 85% opacity), minimal border, no UI chrome. Text: dark sepia ink. Small and readable, not a large dialog box.
HUD indicators: thin, brass-edged, aged parchment backing. Minimal footprint.
Tone: The world is lived-in and ongoing. The aesthetic is a working river port, not a fantasy adventure staging area. Beauty comes from geological specificity (the salt crystal formations, the layered timber city) not from dramatic lighting or magical effects.
Anti-patterns: No "Welcome to Unlimited Worlds" title. No tutorial boxes. No glowing effects anywhere. No bright fantasy sky. No magic visual language. No UI chrome that competes with the world view. Do not make the salt crystals look magical — they are mineral formations. No HUD elements that are not specifically listed above.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific dialogue text and speaker name given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-005-new-player-arrival.html`
