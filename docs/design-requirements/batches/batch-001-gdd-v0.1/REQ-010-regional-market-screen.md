# REQ-010 — Regional Market Screen

**Domain:** Menu/Screen
**GDD Reference:** Section 5.3 (Trade and Markets), Section 5.1 (Gathering — origin geology metadata), Section 2.5 (Weekly Loop — market cycle)
**Phase Relevance:** Phase 2
**Source Session:** Mechanic Designer Session 001 (Question 5: Economy — Trade Subsystem), GDD-v0.1 Section 5.3
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

1. A physically located regional market — not a global auction house. This is the market panel for a Varekian Compact Regional Trade Post in the Varek Delta. Prices reflect local supply and demand, not a global average.
2. Price list with supply/demand indicators: each listed commodity shows current price, a supply/demand trend indicator (up/down/stable), and a geological note indicating why prices are at their current level (referencing world state: "Northern Channel blocked — transit disruption driving salt premium").
3. No global auction house functionality: this market only shows goods physically present at or transported to this location. No remote listing. A "goods in transit" section shows cargo currently en route to this market (player transport convoys in progress), giving a price forecast.
4. Cargo transport flag indicator: for high-value goods in transit, show PvP transport status. Goods in contested-zone transit are flagged as "At risk — PvP territory" with estimated arrival and risk level. Safe-route transport shows no flag.
5. Origin geography on all listed goods: every item for sale shows where it came from, because origin geography affects item properties (Tier 2 and Tier 3 crafting uses the origin data). Buyers can filter by origin region.
6. A "your listings" section showing what the player has listed at this market.
7. The market interface is accessed at the physical market location (a Varekian trade post) — it should feel like a market ledger, not a floating UI.

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact. The regional market screen is the most mercantile surface in the game — it should be the fullest expression of the ledger-aesthetic. Tabular, annotated, origin-geography tagged, price-movement tracked. This interface is where geology becomes commerce.

**Color guidance:** Deep river brown (#3d2b1f) outer frame, aged brass (#b5894f) column dividers and price indicators, tidal grey-green (#7a9e8e) panel backgrounds, salt-flat white (#e8e4d9) text, verdigris (#5a8a7a) for stable price states, mineral amber (#c49a2f) for rising prices, a muted red-brown (#8b3a2f) for falling prices. Biome origin badges use the faction palette system.

**Tone:** A merchant's ledger made interactive. Every column earns its place. Supply/demand trends shown as geological notation (rising terrain = price increase; eroding = falling). Nothing frivolous.

**Anti-patterns:**
- No fantasy auction house visual language (no bidding timers with gavel icons, no magical item glow by rarity)
- No global availability — the market is physically limited to what has been transported here
- No price in "gold coins" — use a resource-backed currency notation (the Varekian Compact uses a "Compact Tally" system referencing bulk commodity values)
- No floating UI without material grounding

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath, a world of geological fantasy. The economy is geography-grounded. Resources are extracted from specific geological locations and their origin matters mechanically — the same material from different biomes has different properties. Trade routes are physical: there is no global auction house. Markets are physically located. Prices reflect regional supply and demand.

THE TRADE SYSTEM:
No global auction house. Markets exist at three scales: (1) Faction capital markets — high liquidity, high prices; (2) Regional trade posts — medium liquidity, regional pricing; (3) Direct player-to-player — negotiated, no location requirement.
Transport is a gameplay layer: moving goods from production zone to consumption market is an economic activity. High-value goods in contested-zone transit are automatically PvP-flagged and visible on the zone map as cargo indicators. Low-value transport in non-contested zones is PvP-protected.
Prices reflect regional supply and demand in near-real-time. A depleted node creates a price spike within 48–72 hours. A new discovery stabilizes prices within 72–96 hours.
Market cycle: supply/demand curves resolve on 5–7 day real-world cycles. Individual large transactions can move prices within a session.

The Varekian Compact uses a commodity-backed currency system called Compact Tallies (CT). Prices are denominated in CT based on bulk commodity reference values.

THE VAREKIAN COMPACT visual identity:
Materials: aged timber, polished river stone, brass fittings, salt crystal accents.
Palette: deep river brown (#3d2b1f) frame, aged brass (#b5894f) column headers and dividers, tidal grey-green (#7a9e8e) panel backgrounds, salt-flat white (#e8e4d9) text, verdigris (#5a8a7a) stable price indicator, mineral amber (#c49a2f) rising price indicator, muted red-brown (#8b3a2f) falling price indicator.
Tone: merchant's ledger made interactive. A tabular, annotated, origin-tagged price list. Every column earns its place.

BIOME ORIGIN BADGES (for goods):
VAREK DELTA: tidal grey-green (#7a9e8e)
SCORCH PLATEAU: forge orange (#d4580a)
DEEPWALKER KARST: mineral amber (#c49a2f)
SHATTER COAST: storm grey-blue (#4a6b7a)

DESIGN SURFACE:
The Regional Market screen for the Varekian Compact Trade Post, Varek's Hold Eastern Dock. Accessed physically at the trade post. Not a floating UI panel — it opens as a full ledger-panel representing the market's inventory.

FUNCTIONAL REQUIREMENTS:
1. Market header:
   "VAREKIAN COMPACT REGIONAL TRADE POST — Eastern Dock, Varek's Hold"
   Current date: "14th Tide-Turn, Year 423 Post-Fracturing"
   Market status: "OPEN — Factor Merik Holst presiding"
   A note about current market conditions: "Advisory: Northern Channel blockage (Day 3) — transit disruption affecting salt and river stone supply. Premium active on affected goods."
2. MAIN PRICE LIST — the primary panel. Show a tabular ledger with these columns:
   COMMODITY | ORIGIN | TIER | CURRENT PRICE | SUPPLY | DEMAND | TREND | NOTE
   Populate with these entries:
   - Salt Crystal (Refined) | VAREK DELTA | T1 | 4.2 CT/unit | Low | High | ↑ RISING | "Channel blockage — 3-day transit disruption. Premium +40% vs. 7-day avg."
   - River Stone (Cut) | VAREK DELTA | T1 | 1.8 CT/unit | Medium | Medium | — STABLE | "Regular supply maintained via south channel."
   - Obsidian Shard | SCORCH PLATEAU | T2 | 12.5 CT/unit | Very Low | High | ↑ RISING | "Ashbound territory access restricted — border incident reducing supply."
   - Forge Iron | SCORCH PLATEAU | T1 | 8.1 CT/unit | Low | High | ↑ RISING | "Same border restriction affecting iron transit. Military demand elevated."
   - Cave Crystal | DEEPWALKER KARST | T2 | 28.0 CT/unit | Very Low | Medium | — STABLE | "Deepwalker supply managed — consistent but limited. No change."
   - Reed Fiber (Woven) | VAREK DELTA | T1 | 0.9 CT/unit | High | Low | ↓ FALLING | "Seasonal oversupply. Reed beds productive following flood season."
   - Sea Glass | SHATTER COAST | T2 | 6.4 CT/unit | Low | Medium | — STABLE | "Shatter Coast supply steady. Tide Compact transport convoy arrived yesterday."
   - Synthesis: Volcanic Compound | SCORCH PLATEAU + DEEPWALKER KARST | T3 | 180 CT/unit | Extremely Low | Very High | ↑ RISING | "Rare — requires multi-biome Synthesis. Only one supplier active in region."
3. GOODS IN TRANSIT section (below main list):
   Title: "In Transit — Expected Arrivals"
   Show two entries:
   - "Obsidian Shard × 40 — From: Scorch Plateau Waypoint 3 — ETA: ~6 hours — Route: Western Pass — Status: SAFE ROUTE — No PvP flag."
   - "Forge Iron × 25 — From: Compact Forward Post, Passage 11 — ETA: ~18 hours — Route: Border Territory (CONTESTED) — Status: AT RISK — PvP flagged. Carrier: DOVEN SALT COMPANY (2-player convoy). Interception risk: Medium."
   The at-risk entry should be visually flagged as a risk state — not alarming, but clearly marked.
4. YOUR LISTINGS section (right panel or bottom panel):
   The player has two items listed:
   - Salt Crystal (Raw) × 30 | VAREK DELTA | T1 | Listed at: 3.1 CT/unit | Market price: 4.2 CT/unit | Status: "Below market — consider adjusting" (flagged in amber)
   - Cave Crystal × 1 | DEEPWALKER KARST | T2 | Listed at: 30 CT/unit | Market price: 28 CT/unit | Status: "Above market — listed 2 days" (flagged in muted red-brown)
5. A compact market trend summary strip at the top or side: "7-day market summary — Varek Delta Eastern Dock: Salt premium active (+40%). Iron supply restricted. Reed oversupply. Synthesis goods scarce."

VISUAL CONSTRAINTS:
Outer frame: deep river brown (#3d2b1f) aged timber, aged brass (#b5894f) corner hardware.
Table header row: aged brass (#b5894f) background, deep brown text.
Table rows: alternating tidal grey-green (#7a9e8e) and slightly lighter (#8aae9e) for readability.
Text: salt-flat white (#e8e4d9) primary.
Price trend indicators: ↑ rising in mineral amber (#c49a2f), ↓ falling in muted red-brown (#8b3a2f), — stable in verdigris (#5a8a7a).
Origin biome badges: small colored tags using faction palette system.
At-risk transit entry: subtle muted red-brown border (#8b3a2f at 60%) and "CONTESTED ROUTE" label in amber.
Tone: merchant's working ledger. Information density is a feature. Every column communicates something economically meaningful. The market's connection to the world state (the channel blockage, the border incident) should be legible in the price data.
Anti-patterns: no gavel/auction icons, no rarity-color-coded item glow, no global availability, no currency called "gold" or "coins," no fantasy auction house aesthetic.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific commodity data, prices, and world-state notes given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-010-regional-market-screen.html`
