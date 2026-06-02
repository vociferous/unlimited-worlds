# REQ-003 — Faction Historical Ledger Notice Board (In-World Object)

**Domain:** World/Environment
**GDD Reference:** Section 7.2 (The Historical Ledger), Section 8.2 (First 30 Minutes — "a public notice board at the dock"), Section 2.1 (Phase 1: Read — "Faction Historical Ledger (public display in town centers)")
**Phase Relevance:** Phase 1
**Source Session:** World Architect Session 001 (Historical Ledger, NPC memory, Varek Delta architecture), Mechanic Designer Session 001 (core loop Read phase, session loop), GDD-v0.1 Sections 7.2 and 8.2
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

1. This is a physical in-world object — a notice board or ledger display mounted in a Varekian Compact town center (specifically the main dock platform area of the Varek Delta). It is NOT a UI screen or menu panel. It is something that exists in the game world that players walk up to and read.
2. The board must display the last 5 Historical Ledger entries for the region. Each entry must show: an event type label (territorial / economic / geological / faction), a timestamp (in-world date format), a location, the factions involved, and a brief event summary (2–3 lines).
3. The board must feel physically constructed — a real object with materials, weathering, mounting hardware, and an evident making tradition. In the Varek Delta, this means wood, brass tacks, oilskin-covered parchment notices, and possibly salt crystal weathering on the lower surfaces where tidal spray reaches.
4. Entries should have a clear visual hierarchy: most recent entry is most prominent (center or top, larger, fresher-looking); older entries are visually aged (more yellowed, smaller, possibly slightly water-damaged).
5. One entry should be flagged as player-relevant (e.g., an entry the viewing player contributed to, shown with a small attribution marker — a brass pin or initialed mark).
6. The board must have a physical frame and mounting that is legible as belonging to the Varekian Compact's visual language — not a generic bulletin board.
7. The surrounding environment context should be visible: the edge of a platform dock, reed water visible below, Varekian Compact architectural elements flanking the board.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact. Materials: aged timber, polished river stone, brass fittings, salt crystal accents, rope and pulley hardware. The board itself should be framed in dark river-weathered timber with brass corner brackets. Parchment notices pinned with brass tacks. Rope detailing on mounting. Salt crystal formations at the base (tidal action).

**Color guidance:**
- Board frame: deep river brown (#3d2b1f) timber
- Brass hardware: aged brass (#b5894f)
- Parchment/paper entries: salt-flat white (#e8e4d9) aging to a deeper cream for older entries
- Text ink: dark sepia, not pure black
- Environmental water/dock: tidal grey-green (#7a9e8e) water tones
- Verdigris accent (#5a8a7a): oxidation on brass fittings, used sparingly
- Salt crystal formations at base: near-white (#e8e4d9) with faint mineral shimmer
- Most recent entry: slightly brighter, less yellowed parchment
- Oldest entry: noticeably yellowed, faint water stain marks at edges

**Tone:** Functional public record. This is not a magical artifact or a glowing UI panel. It is an actual physical notice board where someone with a quill and sealing wax posts official faction communications. Weathered, used, and maintained. The gravitas comes from the density and specificity of the information, not from decorative flourish.

**Anti-patterns:**
- The board must NOT look like a UI overlay or a menu screen with a physical frame around it — it must feel like a three-dimensional object in the game world
- No magical glow, no illuminated runes, no magical text effects
- No purple/fantasy magic color language
- Do not render this as a flat texture panel — give it physical dimensionality through shadow, depth, and material specificity
- Do not use generic fantasy signage (shields, crests with dragons, etc.) — the Varekian Compact uses trade-ledger symbolism: scales, tide markers, route maps

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world of geological fantasy. The world's history is recorded in stone and in the Historical Ledger — a public event log maintained by each of the four major civilizations. The Ledger is the game's persistent memory system: significant events (territorial changes, economic disruptions, geological events, faction battles) are recorded in each faction's Ledger and drive NPC dialogue, player reputation, and world state.

The four civilizations:
- THE VAREKIAN COMPACT: River delta and lowland basin civilization. Pragmatic merchants and hydraulic engineers who survived the Fracturing (a geological catastrophe 400 years ago) by adaptation rather than retreat. They value contracts, information, and water management. Their cities are built on raised timber platforms above the flood plain. Visual identity: aged timber, polished river stone, brass fittings, salt crystal formations from tidal deposits, rope and pulley hardware. Palette: deep river brown timber (#3d2b1f), aged brass hardware (#b5894f), tidal grey-green water (#7a9e8e), salt-flat white parchment (#e8e4d9), verdigris oxidation (#5a8a7a). Tone: mercantile-ledger aesthetic — information-dense, tabular, nothing decorative that is not load-bearing.
- THE ASHBOUND: Volcanic plateau civilization. Militaristic theocrats who see the Fracturing as divine selection. Palette: volcanic black, forge orange (#d4580a), ash grey (#6b6359).
- THE DEEPWALKERS: Underground karst civilization, ancient and scholarly. Palette: cave black, bioluminescent blue-green, mineral amber (#c49a2f).
- THE TIDE COMPACT: Young coastal confederation, exploratory and meritocratic. Palette: storm grey-blue, salvage rust-orange, sea-glass green.

THE HISTORICAL LEDGER:
Each faction maintains a Historical Ledger — a public record of the last N significant events that affected that faction. Significance is measured by impact on: population, territory, resource access, political alignment, and threat level. The Ledger entry format: timestamp / event type / location / factions involved / players involved / effect summary.

When players interact with NPCs, those NPCs' dialogue and behavior are derived from the Ledger's current state. An NPC blacksmith references current trade disruptions. A soldier NPC references recent territorial conflicts. The Ledger is visible to all players — it is a public historical record.

The Varek Delta Historical Ledger is posted on public notice boards in town centers and dock areas. The Ledger creates a "newspaper effect": players who log in after time away check the board to see what changed.

THE VAREK DELTA:
The default starting zone. A flooded river plain with shifting sandbars, dense reed networks, and a mix of fresh and salt water after the Fracturing disrupted the water table. Salt crystal formations rise from the shallows in some areas. The Varekian Compact's major city, Varek's Hold, is built on raised timber platforms above the floodplain — a layered, industrial, complex settlement already in operation before the player arrives. The platform dock area is where players disembark from trade barges.

DESIGN SURFACE:
A physical in-world notice board object — the Varekian Compact Historical Ledger board, as it appears mounted at the main dock platform in Varek's Hold. This is NOT a UI screen or menu overlay. It is a three-dimensional physical object in the game world. It should be rendered as a view of the object in its environment — the player would walk up to this board and read it. Show the surrounding dock environment as context.

FUNCTIONAL REQUIREMENTS:
1. The board is a large timber-framed notice board mounted on the dock platform, with brass corner brackets and rope-lashed support posts. It should feel architecturally coherent with Varekian platform construction — horizontal, modular, practical.
2. Display 5 Historical Ledger entries on the board as parchment notices, pinned with brass tacks. Entries are ordered most-recent to oldest (top to bottom, or center to edge). Use this specific content:

ENTRY 1 (most recent — 2 days ago, fresh parchment):
Type: ECONOMIC
Date: 14th Tide-Turn, Year 423 Post-Fracturing
Location: Northern Channel Approaches
Factions: Varekian Compact
Summary: "Sandbar formation confirmed at Northern Channel kilometer 7. Merchant transit delayed estimated 2 days pending Compact survey. Alternate route via Reed Bed passage authorized by Factor Merik Holst."

ENTRY 2 (4 days ago):
Type: TERRITORIAL
Date: 12th Tide-Turn, Year 423 Post-Fracturing
Location: Eastern Salt Flat, Zone 3
Factions: Varekian Compact / Tide Compact
Summary: "Salt crystal formation staked by Varekian Compact survey team following contested approach from Tide Compact scouts. Claim registered with Factor's post. Dispute note filed by Tide Compact representative."

ENTRY 3 (9 days ago):
Type: GEOLOGICAL
Date: 7th Tide-Turn, Year 423 Post-Fracturing
Location: Platform District 4, Sub-foundation Level
Factions: Varekian Compact / Deepwalkers
Summary: "Deepwalker geological surveyor confirms subsurface saline cavity beneath District 4. Compact plans for cavity drainage for salt extraction. Deepwalker formal objection filed. Review scheduled."

ENTRY 4 (16 days ago, slightly yellowed):
Type: ECONOMIC
Date: Last-Ebb, 28th, Year 423 Post-Fracturing
Location: Varek's Hold Central Market
Factions: Varekian Compact
Summary: "Quarterly river-stone supply levy completed. Trade post inventory restocked. Iron bracket price stabilized following 3-week shortage attributed to Ashbound border incident at Passage 11."

ENTRY 5 (oldest — 22 days ago, yellowed, minor water stain at bottom edge):
Type: TERRITORIAL
Date: Last-Ebb, 22nd, Year 423 Post-Fracturing
Location: Reed Bed Passage, West Approach
Factions: Varekian Compact / Tide Compact
Summary: "Western reed bed passage rights formally registered to Varekian Compact following survey completion. Tide Compact access rights confirmed for transit (non-extraction). Route survey attribution: [Player name stamped in brass: KAEL DURST]."

3. Entry 5 should have a small brass attribution stamp showing a player name — "KAEL DURST" — indicating this player's contribution was Ledger-significant. This is the player-attribution marker.
4. The most recent entry (Entry 1) should be visually the freshest — bright parchment, clean edges, dark clear ink. The oldest entry (Entry 5) should be visually the most aged — yellowed parchment, slightly water-stained, ink slightly faded.
5. Show the dock environment: the board is mounted on a timber post at the edge of a raised platform. Below and behind the platform, show dark tidal water with salt crystal formations visible above the waterline. Rope detailing on the post and platform edge. Salt crystal mineral deposits at the base of the post from tide action.
6. The Varekian Compact's ledger-mark symbol should appear at the top of the board frame — a simple trade symbol (scales in balance, or a tide-line marker, or a stylized anchor-and-route motif) — not a fantasy crest.

VISUAL CONSTRAINTS:
Faction: Varekian Compact.
Board frame: deep river brown (#3d2b1f) aged timber, aged brass (#b5894f) corner brackets and tack heads.
Parchment entries: fresh entries are near salt-flat white (#e8e4d9); oldest entry is deeper cream/yellowed with water stain tinting.
Text ink: dark sepia — warm dark brown, not pure black.
Water below dock: tidal grey-green (#7a9e8e).
Salt crystal formations: near-white to pale grey (#e8e4d9 to #c8c4b8) with faint mineral shimmer suggested via subtle gradient or highlight.
Verdigris (#5a8a7a): oxidation on brass hardware, used sparingly as aging detail.
Rope: natural hemp tan.
Tone: Functional public record in a working port. Weathered, used, maintained. The gravitas comes from information density and physical materiality, not decorative flourish.
Anti-patterns: The board must NOT look like a UI panel or a game menu — it must read as a three-dimensional physical object. No magical glow. No illuminated runes. No generic fantasy heraldry (shields with dragons). No purple/void color. Varekian trade symbols only: scales, tide-lines, route markers, compass roses, ledger marks.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific placeholder data given above (not "Lorem ipsum")
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-003-ledger-notice-board.html`
