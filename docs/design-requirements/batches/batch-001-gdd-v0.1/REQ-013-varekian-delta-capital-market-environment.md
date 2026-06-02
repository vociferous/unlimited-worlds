# REQ-013 — Varekian Delta Capital Market (In-World Environment/Architecture)

**Domain:** World/Environment
**GDD Reference:** Section 5.3 (Trade and Markets — "Faction capital markets: high liquidity, large selection, high prices"), Section 7.1 (The Varekian Compact — architecture, cultural identity), World Architect Session 001 (Varek Delta biome, Varekian architecture)
**Phase Relevance:** Phase 3+
**Source Session:** World Architect Session 001 (Varekian Compact architecture — horizontal, modular, platform cities above floodplain), Mechanic Designer Session 001 (trade subsystem — physically located markets), GDD-v0.1 Sections 5.3 and 7.1
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

1. This is an in-world architectural/environmental design exploration — not a UI screen. The design surface is the physical market hall space itself: the building, its interior spatial logic, its materials, and how it embodies Varekian Compact values.
2. The capital market is the economic heart of Varek's Hold — the highest-liquidity, highest-volume trading location in the Varekian Compact faction territory. It should feel like the most impressive Varekian building the player has entered, without betraying the faction's horizontal, modular, pragmatic architectural identity.
3. Show the market hall exterior approach and interior in a single scene or a diptych — the player's experience of arriving at and entering the space.
4. Key architectural features to include: raised platform construction above floodplain level, salt crystal formations integrated into the structure's foundation supports, brass hardware and mechanical elements (rope-and-pulley systems for goods movement), a large central trading floor with market stalls, a Ledger board prominently mounted, natural light filtered through slatted timber above. The space should feel like a working industrial market, not a decorative palace.
5. The space must communicate: this is where the Varekian Compact's commercial values are most fully expressed — information dense, mechanically sophisticated, built to move goods and record transactions, not to impress aesthetically. Its impressiveness is functional.
6. Human-scale detail: show merchants, trade transactions, goods in transit, the physical infrastructure of commerce. The space is alive with economic activity.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact at its most fully realized. Every architectural element flows from the same material logic as the HUD and UI elements, but at physical scale.

**Materials:** Aged timber (deep river brown #3d2b1f) for primary structural elements, polished river stone for floor surfaces, brass fittings (#b5894f) for hardware (rope-and-pulley systems, column brackets, stall frames), salt crystal formations at the base of foundation piles (natural accumulation from tidal action), woven reed mats and canvas awnings, hemp rope rigging.

**Color guidance:** The space is predominantly deep timber browns (#3d2b1f to #5a3a1f), with brass glints (#b5894f) throughout as hardware, salt-flat white (#e8e4d9) for salt crystal formations and natural light filtering, tidal grey-green (#7a9e8e) from water visible below the platform gaps and through the open market edges.

**Tone:** Industrial mercantile. The market hall is a machine for commerce, designed by engineers and merchants, not architects. Its beauty comes from the precision of its construction and the density of activity within it.

**Anti-patterns:**
- No decorative fantasy palace architecture
- No grand ornamental entrance arches (the scale comes from functional span, not decorative height)
- No magical glowing elements
- No generic fantasy market (no colorful tent bazaar aesthetic)
- The salt crystal formations must look geological, not magical

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath ("the Dern"), a world of geological fantasy. The Varekian Compact is the game's default faction — a river delta civilization of pragmatic merchants and hydraulic engineers who survived the Fracturing (a geological catastrophe 400 years ago) by adaptation.

THE VAREKIAN COMPACT:
Cultural identity: pragmatic, mercantile, engineering-minded. They believe in contracts, hydraulics, and knowing where the next trade comes from. Their cities are built on raised timber platforms above the delta floodplain. Architecture: horizontal, modular, low, wide, designed to be relocated if necessary. Their aesthetic is that of a working port civilization — nothing decorative that is not load-bearing.
Visual materials: aged timber (#3d2b1f to #5a3a1f range), polished river stone floors, brass fittings (#b5894f), salt crystal formations from tidal deposits (#e8e4d9 mineral columns), rope and pulley hardware, woven reed and canvas awnings.
Palette: deep river brown timber (#3d2b1f), aged brass (#b5894f), tidal grey-green water (#7a9e8e), salt-flat white (#e8e4d9), verdigris oxidation (#5a8a7a).
The Varek Delta biome: flooded river plains, shifting sandbars, dense reed networks. Fresh and salt water mix at unpredictable layers after the Fracturing disrupted the water table. Salt crystal formations rise from the shallows where the water table boundary creates crystallization — some meters tall.

THE CAPITAL MARKET:
The capital market in Varek's Hold is the highest-liquidity trading location in Varekian Compact territory. It is physically located — not a global auction house. Prices reflect actual supply and demand. Goods must be physically transported here to be sold. Faction capital markets have high prices (intermediary markup). This is where the economy of the Dern most visibly operates.

The market uses a commodity-backed currency system (Compact Tallies). The Historical Ledger for the Varek Delta region is posted prominently in the market hall — NPCs, players, and merchants reference current Ledger state when making decisions.

DESIGN SURFACE:
An environmental and architectural design exploration for the Varekian Delta Capital Market hall in Varek's Hold — the physical market space itself. Not a UI screen: this is the in-world architecture and environment that players walk into. Show the space in two views within a single document:
VIEW A: The exterior approach — what the player sees walking up to the market hall from the main platform dock. The building's facade, its position on the platform city above the delta water.
VIEW B: The interior market floor — what the player sees upon entering. The main trading hall, stalls, merchants, goods in transit, the Ledger board.

FUNCTIONAL REQUIREMENTS:
1. VIEW A — EXTERIOR APPROACH:
   The market hall is a large timber-frame structure on raised platform stilts. Key features to show:
   - The building sits above the waterline — visible below the platform deck are dark delta water and salt crystal formations rising from the shallows.
   - Horizontal architectural proportions: wide, low relative to its scale, with modular expansion sections visible (the market has been extended over the years).
   - Large cargo-loading access on the ground level for transport ships — a purpose-built loading dock below the main trading floor, accessible by rope-and-pulley goods lift.
   - Brass hardware visible on structural elements: column brackets, balcony rail fittings, the goods lift mechanism.
   - A large market signboard or trade plaque: "VAREKIAN COMPACT TRADE AUTHORITY — VAREK'S HOLD CENTRAL MARKET — Est. Year 47 Post-Fracturing."
   - Reed canvas awnings over exterior approach (weathered, practical, not decorative).
   - Salt crystal formations at the base of the foundation piles — natural tidal accumulation over centuries.
   - Other merchants/barges visible approaching from the river side — the space is alive with economic activity.
2. VIEW B — INTERIOR MARKET FLOOR:
   A large covered trading floor. Key features:
   - High timber-beam ceiling with slatted panels allowing diffuse natural light — industrial, not grand.
   - Rows of market stalls on either side of a central trading floor. Stall frames are brass-fitted timber modules — all the same base module, reflecting Varekian modular construction logic. Merchants have personalized their stalls with goods display.
   - Rope-and-pulley overhead freight systems visible in the ceiling infrastructure — goods crates moving on tracks above the stall rows.
   - A central open space with direct negotiation tables (for high-value direct trade between players and between merchants).
   - The Historical Ledger board: prominently mounted on the main wall at the far end of the trading floor. Large, clearly legible from across the floor. Shows current market conditions derived from Ledger events — "Northern Channel blocked: Salt premium active. Iron supply restricted." The board is the market's public information system.
   - Specific goods visible in the scene: salt crystal formations in display cases on stalls, river stone blocks stacked near one stall, obsidian shards in a secure case (Scorch Plateau goods — premium), rope and canvas goods.
   - Economic life: merchants in conversation, a transaction being made at a central table, a cargo delivery being assessed.
   - Stone flooring at ground level with embedded salt crystal fragments in the stone — geological material even in the floor.
3. Both views should convey: this is a place built by engineers for commerce, where function has accumulated into a kind of functional beauty. The space has depth of use — it has been operating for nearly 400 years (since Year 47 Post-Fracturing). It is worn in the right places, maintained where it matters.

VISUAL CONSTRAINTS:
Primary structural palette: deep timber browns (#3d2b1f to #5a3a1f), brass hardware (#b5894f), polished stone floors (neutral grey-brown), salt-flat white salt crystal accents (#e8e4d9).
Water below the platform: tidal grey-green (#7a9e8e) visible through platform gaps and around the foundation piles.
Interior light: diffuse, coming through slatted ceiling panels. Warm but not dramatic. Supplemented by brass lanterns casting local warm light. No magical glow — oil lamp or reflective brass light.
Salt crystals: pale white to mineral grey mineral formations, geological in character (jagged, column-shaped, formation-based), NOT magical glowing gems.
Canvas awnings/coverings: weathered natural hemp/linen tone — off-white to tan.
Tone: Industrial mercantile. A working machine for commerce. Its scale and complexity come from functional necessity, not decoration.
Anti-patterns: No fantasy palace decorations. No ornamental arches for ornament's sake. No magical glowing elements. No generic tent-market bazaar aesthetic. No colorful fantasy market visual language. Salt crystals must look geological, not magical. The space should feel like a grain exchange or a commodities market, not a fantasy vendor district.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Show both VIEW A (exterior) and VIEW B (interior) in the single document
- Annotate non-obvious layout zones with HTML comments
- Use CSS to create the environmental illustration — architectural scene composition
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-013-varekian-capital-market-environment.html`
