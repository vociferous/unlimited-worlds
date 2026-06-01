# Core Gameplay Loop
**Version:** 0.1 (Mechanic Designer Session 001)
**Date:** 2026-05-31
**Author:** AGT-002 Mechanic Designer
**Status:** Draft — ready for GDD Writer formalization
**Depends On:** World Primer v0.1 (docs/lore/world-primer.md)

---

## Overview

The Unlimited Worlds gameplay loop is built around a single operational principle: **the player reads the world's current geological and political state, takes an action that changes it, and leaves a traceable mark — then reads again to see how the world has responded.**

Every mechanic in the game — combat, crafting, exploration, economy, progression, land ownership — is an expression of this Read → Act → Mark cycle. The player is not progressing through a story the developers wrote. They are participating in a world that is already in motion.

---

## 1. The Core Loop (5–15 Minutes)

The core loop is the moment-to-moment repeating cycle. Every player archetype — combat, gatherer, crafter, explorer, faction operative — performs this same three-phase loop. The specific activities within each phase differ by archetype; the structure does not.

### Phase 1: Read (1–3 minutes)

The player observes the world's current state before acting. Reading is an active skill with mechanical depth — not downtime.

**What the player reads:**
- **Geological indicators**: visual and auditory cues about the zone's current tectonic state (cracking sounds, sulfur smell in new areas, unusual crystal growth, water table shifts)
- **The faction Historical Ledger**: the public record of recent significant faction events; visible in town centers and accessible via a faction UI panel
- **NPC behavioral patterns**: patrol weight, merchant inventory availability, NPC dialogue reflecting current conditions
- **Resource field state**: visible depletion status of extractable nodes; claim stakes marking other players' territory

**Mechanical support for Reading:**
Players with advanced Reading or Resonance disciplines see more from the same environment. A Surface-level player sees that a cave entrance is unusual. A Formation-level player reads that the geological strata above indicate a rare mineral upwelling inside. A Mantle-level player reads that the upwelling matches Founder-era resonance signatures. The same world delivers different information to players with different geological depth — this is a primary progression reward.

### Phase 2: Act (5–10 minutes)

The player executes a chosen activity against the world state they have read. The Act phase produces two outputs: a **tangible result** (resources, damage dealt, territory changed, information recorded) and a **world-state change** that the Act phase leads into.

**Act types by archetype:**

| Archetype | Primary Act | Tangible Result |
|---|---|---|
| Combat | Engage in a contested zone; defend or take territory | Territory state change; Ledger-eligible event if significant |
| Gatherer | Extract from a resource node using discipline techniques | Raw materials; node depletion; discovery documentation if first-find |
| Crafter | Transform raw materials into refined goods or structures | Crafted goods with origin-geology properties |
| Explorer | Move into unmapped or procedurally generated territory | Cartographic records; Founder ruin discovery; mystery documentation |
| Faction operative | Execute a mission that registers at faction-Ledger scale | Faction metric change; Ledger entry if threshold met |

**Key rule:** The Act phase should never be fully automated or passive. Every major activity requires decisions:
- Gatherers choose extraction method (speed vs. yield vs. terrain preservation)
- Crafters choose material combinations that determine the properties of the output
- Combat players choose Terrain Stance based on the geological environment
- Explorers choose documentation depth (quick survey vs. full geological record)

### Phase 3: Mark (30 seconds–2 minutes)

The world records what the player did. The Mark phase is explicit and visible to other players — it is what closes the loop and makes the game feel alive.

**Forms of marking:**
- **Resource node depletion**: the node shows reduced yield; other players can see it
- **Claim Stake placement**: a visible world marker declaring extraction priority
- **Faction Ledger update**: if the Act met the significance threshold, an entry is created that other players can read
- **Territory state change**: if the Act involved land, the zone control indicator reflects it
- **Cartographic update**: exploration results are added to the shared world map with the player's attribution
- **Geological imprint**: certain high-significance Acts (Anchor installation interaction, terrain destruction, major geological event participation) permanently alter the zone in ways that persist indefinitely

The Mark phase is the mechanism by which True Persistence is delivered at the core loop level. Every loop cycle deposits a layer of consequence.

---

## 2. Outer Loops

### Session Loop (~1 Hour)

A one-hour session comprises 4–6 core loop cycles plus three meta-activities that give the session meaning beyond individual cycles:

**One faction-relevant action per session:**
An action that touches the faction Historical Ledger or moves a faction metric. Does not need to be dramatic — a significant mineral delivery to a trade post counts. The player should end every session having done something the faction will notice, even if only at the smallest Ledger-eligible level.

**One exploration or intelligence action per session:**
Discovering something new (resource vein, geological anomaly, terrain change) or gathering intelligence (NPC behavior patterns, Ledger changes, market state) that informs the next session's Read phase. This is the hook that turns the session loop into the weekly loop.

**One economic transaction per session:**
Selling crafted goods, buying materials from another player, engaging a trade post, or contributing to a faction supply chain. This is the glue that makes the economy feel real rather than a separate system.

**The session ends with evidence of external change.** The world is not identical to how it was when the player logged in. A territory marker has moved, a Ledger has been updated, a node has been depleted, a map has a new entry.

### Weekly Loop

The aggregate of 3–7 sessions. Three cycles run concurrently at the weekly scale:

**Faction event cycle (3–5 days):**
Major faction events — territorial disputes, geological anomaly discoveries, resource crises, political negotiations — fire on a 3–5 day real-world cycle. Players who log in during an active event experience a world under pressure. Those who miss it return to a world where the outcome has been recorded in the Ledger. The Ledger creates the "newspaper effect" — players returning after a few days feel compelled to read what happened.

**Geological cycle (7–10 days):**
Tectonic precursor events — tremors reported by NPCs, anomalous tidal behavior, unusual NPC migration, new geological indicator readings — are observable over 7–10 day windows before a generation or transformation event fires. Players who are present during the window piece together the forecast. Players who miss it encounter the outcome. Forecasting is a collaborative player activity; Reading-discipline players can publish predictions that other players act on.

**Market cycle (5–7 days):**
Resource supply and demand curves resolve on weekly timescales. A depleted node creates a price spike within 48–72 hours. A new vein discovery stabilizes prices within 72–96 hours. Players managing economic positions require weekly attention but not daily mandatory sessions.

### Long-Term Progression Arc (Months / Years)

The long-term arc answers: what is the player building toward over many months of play?

**The Geological Legacy System**

A player's character builds a Geological Legacy — a persistent, non-resettable record of their impact on the Dern's geology, economy, and faction history. Legacy is not a power score. It is a historical record with mechanical consequences.

**Legacy components:**

| Component | Description | Persistence |
|---|---|---|
| Territorial Imprint | Land claimed, developed, defended, or destroyed | Persists until another player changes it |
| Faction Ledger Entries | Events the player triggered that entered civilizational memory | Active until Legend Layer decay; then persists as legend text |
| Geological Marks | Resource nodes discovered, terrain altered, Anchor installations activated or destroyed | Permanent changes to world geography |
| Civilizational Contribution Score | Faction-specific measure of contribution to faction position | Unlocks access to higher-tier faction content |

**The key design principle:** Legacy is not power — it is access and meaning. A player with a 2-year Legacy has access to deeper faction content, greater historical context, and more meaningful Ledger entries. They are not twice as powerful in combat as a new player. A new player can influence the world and threaten a veteran's territory.

---

## 3. Combat System

### Direction: Modified Hybrid — Geological Combat

**System classification:** Hybrid targeting (positional awareness + skill slots) with a Terrain Stance layer that introduces biome-specific combat modifiers.

Pure real-time action combat is not suitable at 500+ players per zone (technical scale constraints, accessibility). Pure tab-target does not express the geological setting. The hybrid approach with a geological layer delivers both scale and world-identity.

### The Terrain Stance System

Every zone has a geological state (rock type, mineral composition, moisture, seismic activity). Players who have developed faction skills can read this state and adopt a Terrain Stance — a combat modifier reflecting deliberate use of the environment's geological character.

**Terrain Stance examples:**

**Ashbound Volcanic Stance** (Scorch Plateau):
- Activates on obsidian floor surfaces
- Grants: heat damage rider on physical abilities; access to magma vent eruption triggers (environmental attack mechanic activated by accumulated heat damage)
- Costs: reduced movement speed (terrain is unstable); vulnerability to cold-type effects

**Varekian Salt Attunement** (Varek Delta salt flat zones):
- Activates on crystalline salt terrain
- Grants: crystal fragmentation creates area-denial zones when struck; high-ground advantage mechanic on salt formations; salt storm trigger if formation damage threshold is reached
- Costs: salt crystal terrain is visible to all players, so movement patterns are telegraphed

**Deepwalker Deep Sense** (underground karst):
- Activates underground or in cave-adjacent environments
- Grants: darkness exploitation (reduced enemy detection range for Deepwalker-side); sound-based positioning awareness (players hear enemy movement before seeing it); collapse trap mechanic (triggering ceiling instability in geologically weak sections)
- Costs: weaker in open-air environments; stances require 3-second channel to establish, leaving the player briefly vulnerable

**Tide Compact Open Water Stance** (coastal/maritime zones):
- Activates near water in coastal environments
- Grants: flanking speed bonus when attacking from a water-adjacent position; weather exploitation (increased damage during active storm events); withdrawal bonus (reduced cast interruption when breaking combat toward water)
- Costs: only operates near water; no terrain-denial capability

### Faction Combat Identities

| Faction | Combat Identity | Primary Role |
|---|---|---|
| Varekian Compact | Battlefield control and redirection | CC, terrain manipulation, debuff |
| Ashbound | Aggressive overwhelming force | Offensive damage, terrain destruction |
| Deepwalkers | Patience and attrition | Environment exploitation, disorientation, traps |
| Tide Compact | Speed and adaptability | Flanking, scouting, controlled withdrawal |

### Large-Scale Combat (500+ Players)

At 500+ player scale, individual Terrain Stance mechanics aggregate into zone-level effects:
- Mass Ashbound combat activity in a volcanic zone can trigger server-resolved geological events (eruption events) that affect the entire zone's combat state for a period
- Mass Varekian salt manipulation can trigger salt storm zone events, affecting visibility and movement for all zone participants
- These zone-level effects are pre-announced by escalating geological indicators — they do not fire without warning

Technical note for GDD formalization: Terrain Stance state is zone-managed, not per-player per-frame. State updates on zone event ticks, not on per-hit calculation. This is the primary reason the system is scalable.

---

## 4. Character Progression

### System: Geological Discipline System

Character progression is organized around four **Geological Disciplines** — domains of understanding of the Dern's geological mechanics. Disciplines are not classes. They define what the player understands about the world and therefore what they can do with it.

### The Four Disciplines

**Resonance**
Understanding and manipulation of geological resonance — the deep language of the Dern and the operating language of Founder technology.
- Primary affiliation: Deepwalker Compact (not locked to this faction)
- Combat role: support and battlefield control
- Economic role: Founder installation investigation, rare material identification, geological forecasting
- Unique capability: the only discipline with full Anchor Network interface capability at advanced depths

**Shaping**
Forceful geological manipulation — volcanics, seismic events, terrain modification.
- Primary affiliation: The Ashbound
- Combat role: offensive devastation and terrain destruction
- Economic role: mine development, terrain clearing, large-scale construction, fortification
- Unique capability: the only discipline capable of permanent irreversible terrain alteration

**Reading**
Geological intelligence — extracting information from terrain, predicting changes, exploiting economic opportunity.
- Primary affiliation: Varekian Compact
- Combat role: intelligence and tactical support
- Economic role: resource forecasting, market positioning, geological survey for hire
- Unique capability: the highest yield from geological observation; best information quality in the Read phase

**Charting**
Geographical mastery — moving through, documenting, and claiming new territory.
- Primary affiliation: Tide Compact
- Combat role: scouting and mobile skirmishing
- Economic role: exploration, first-finder bonuses, cartographic trade goods, salvage
- Unique capability: highest movement efficiency in unmapped territory; access to Tide Compact's procedural frontier infrastructure

### Strata Depth

Progression within a discipline is measured in **Strata** — a geological metaphor for depth of understanding.

| Strata Range | Geological Name | Equivalent Level |
|---|---|---|
| 1–10 | Surface Understanding | Novice |
| 11–25 | Formation Understanding | Intermediate |
| 26–40 | Mantle Understanding | Advanced |
| 41–50 | Core Understanding | Expert |

Core Understanding (41–50) represents knowledge equivalent to Founder geological mastery. Very few players reach this depth in any discipline. It is not required to participate meaningfully in the game.

**Cross-discipline training:**
Players choose a primary discipline at character creation (connected to their starting faction's expertise). Over time, they can develop secondary disciplines through world engagement. A primary Resonance practitioner who develops secondary Reading has a distinct analytical advantage — they can both read and interface with geological formations. Cross-training is meaningful but never replaces depth in the primary discipline.

### Progression Inputs

Progression comes from doing, not from killing:
- Engaging with geological features relevant to your discipline
- Participating in faction-relevant events that enter the Historical Ledger
- Discovery actions (first documentation of a new geological formation grants a discipline depth bonus)
- Mentorship (teaching lower-depth players, rewarded with modest discipline progression)

**World-gated depth progression:**
Advancing from Formation to Mantle Understanding in any discipline requires direct engagement with a Mantle-depth geological formation in the world — an actual location, not just accumulated XP. This prevents purely mechanical grind advancement and ensures that progression requires genuine world engagement.

### New Player Competitiveness

Combat power differential between Strata is compressed. The gap between a Surface Shaper and a Core Shaper is meaningful in breadth of capability and precision — not in raw combat power multiplied tenfold.

New players in newly generated procedural regions begin on equal geological footing with veterans — no one has Mantle-depth knowledge of a zone that was generated last week. Tectonic disruption events in established zones partially reset veteran contextual advantage, because the geological state they mastered has changed.

---

## 5. Economy Loop

### Economy Overview

The Unlimited Worlds economy is a geography-grounded supply chain: resources are extracted from specific geological locations, transformed through geological crafting techniques, and traded across a physically located market network. Every stage of the chain expresses the geological theme.

### Gathering

**Core principle:** Extraction is not passive.

Resource nodes are geological formations that require geological knowledge to extract efficiently. The gathering loop involves three active decisions:

**1. Survey (Reading discipline):**
Before extracting, a player with Reading discipline surveys the formation. Survey reveals: predicted quality tier, approximate yield, structural risk (will aggressive extraction destabilize the surrounding terrain?), and geological characteristics relevant to crafting use. Players without Reading discipline extract without this information — they get what they get.

**2. Extraction method choice:**

| Method | Speed | Yield | Terrain Effect | Discipline Required |
|---|---|---|---|---|
| Blast Extraction | Fast | Moderate | Damages surrounding terrain; reduces total node yield | Shaping |
| Precision Extraction | Slow | High | Preserves terrain; maximal node yield | Resonance |
| Standard Extraction | Medium | Standard | Neutral | None |

**3. Node depletion:**
All resource nodes have finite yield. Depletion is visible to other players. Regeneration rate scales with local geological activity:
- Tectonically active zones: faster regeneration (new material upwelling)
- Stable zones: slower regeneration
- Magically disrupted zones: unpredictable regeneration

**First-finder bonus:** The first player to discover and document a new resource node receives a permanent minor yield bonus on that node. This is recorded in their Geological Legacy and visible to other players as a discovery attribution.

**Common Ground nodes:** Every zone contains designated Common Ground areas with reliably respawning, lower-yield nodes. These ensure that players who log in infrequently always have access to basic gathering, regardless of whether high-yield deep-field nodes are depleted.

### Crafting

**Core principle:** Crafting is geological transformation. The origin geology of the source material affects the properties of the output.

**Three tiers:**

**Tier 1 — Raw Processing:**
Convert extracted materials to workable stock (ore to ingots, mineral formations to powders). No special discipline required. Available from basic faction infrastructure.

**Tier 2 — Geological Crafting:**
Apply discipline knowledge to produce goods with properties derived from their origin geology. A blade crafted from Scorch Plateau obsidian has fire-affinity properties. The same blade crafted from Shatter Coast mineral deposits has salt-corrosion resistance properties. Origin geology is not flavor text — it produces mechanically distinct item properties.

**Tier 3 — Synthesis:**
Combine materials from two or more geological sources to produce hybrid materials with properties unavailable from either source alone. Requires advanced discipline knowledge. Synthesis is the game's highest-value crafting output and the primary driver of inter-faction resource trade (Synthesis demands materials from multiple biomes, which no single faction fully controls).

### Trade and Markets

**Physical market locations only.** No global auction house.

| Market Type | Liquidity | Price Level | Notes |
|---|---|---|---|
| Faction capital markets | High | High (intermediary markup) | Accessible across faction territory |
| Regional trade posts | Medium | Regional supply/demand | Prices reflect local conditions |
| Direct player-to-player | Variable | Negotiated | No fee; requires finding counterparty |

**Transport is a gameplay layer.** Moving goods from extraction zone to consumption market produces price differential (profit), but also creates risk (theft/interdiction, geological hazards, time/distance cost). High-value cargo moves in organized convoys — a cooperative social mechanic. Solo transport of low-value goods is safe in most zones.

**Geography as economic asset (examples):**

*Scenario A — Resource control:*
A guild controlling the primary salt flat near the Varek Delta controls: a direct extraction income stream; the ability to charge access fees; supply restriction (drives up prices in salt-dependent markets); a diplomatic trade chip usable with other factions.

*Scenario B — Anchor installation activation:*
An installation is activated and stabilizes a previously volatile volcanic zone. Land that was previously uninhabitable is now viable. Players who predicted this (through Reading/Resonance geological forecasting) and established claims ahead of stabilization have made a high-return investment. Players who act quickly post-stabilization get second-mover advantage. Players who ignore it find the zone already claimed.

Geography changes = economic shocks. The economy responds in real time to world events.

---

## 6. Land Ownership

### Three-Tier Framework

**Tier 1 — Exploration Rights (default state of all land)**

Any player can be present in any zone and extract resources freely. This is the permanent baseline. The world is always accessible. No form of ownership can block a player from passing through or making basic use of land.

**Tier 2 — Claim Stakes (temporary, contested)**

Players can assert extraction priority by placing a Claim Stake on a resource-rich area.

- Visible to all players in the world and on the zone map
- Duration: 72 real-world hours; must be renewed to persist
- Effect: extraction priority (other players can still extract from the staked area, but at reduced yield; automated bots and unattended extraction are blocked entirely for non-holders)
- Contestation: any player can challenge a stake, triggering a **Contention Event**
- A stake that goes undefended for 12 consecutive hours in a contested zone automatically enters Contention status

*(Contention Event mechanic details require System Designer specification — see Open Questions.)*

**Tier 3 — Development Rights (permanent, faction-legible)**

For permanent structures — settlements, fortifications, trade posts, Anchor control points — players purchase Development Rights from their faction. Requirements:
- The zone must be accessible to the purchasing faction
- The zone must have geological stability appropriate to the structure type (disclosed at purchase)
- The player or guild must meet a minimum Civilizational Contribution Score threshold for their faction
- Payment in resources appropriate to the structure type

Development Rights are persistent until:
- Forcibly taken through a siege mechanic
- Rendered uninhabitable by a geological event that was not mitigated (tectonic insurance can reduce this risk)
- Abandoned by the owner (decay timeline below)

**Decay Timeline for Abandoned Structures:**

| Time Since Last Owner Activity | Structure State |
|---|---|
| 30 days | Decay begins; structure shows visible deterioration |
| 60 days | Abandoned status; faction ownership claim lapses; any player may occupy |
| 90 days | Advanced deterioration; reduced functional capacity |
| 180 days | Ruin state; historically significant but no longer functional |

Structures with active Ledger entries (historical significance) decay more slowly — their civilizational significance extends their lifespan. Very significant structures may persist as ruins indefinitely, entering the Legend Layer as permanent historical landmarks.

### Building on Development Rights Land

Players may construct buildings and infrastructure within their Development Rights territory. Construction rules:
- Resources required scale with structure size and complexity
- Structures must use materials architecturally appropriate to the biome's geological character; building against geological logic (e.g., a platform-city structure design on a seismically active volcanic plateau without adaptive foundation work) produces structural instability over time
- All player-built structures are visible in the world to all players and contribute to civilizational density (which feeds the demographic procedural generation trigger)
- Destroyed structures leave ruins — salvage sites and, eventually, Legend Layer historical remnants

### Terrain Destruction

The Shaping discipline enables terrain destruction. Rules:
- Requires significant Shaping discipline depth (Formation-level minimum; Mantle-level for major terrain alteration)
- Consumes costly Shaping resources
- Produces faction diplomatic consequences visible to the Historical Ledger if the destruction is significant
- Destroyed terrain takes a new geological path; it does not regenerate to its previous state
- Releases materials at lower yield than proper extraction — destruction is not economically efficient

Terrain destruction is a weapon, not a mining shortcut. The mechanic's cost structure ensures it is used as a deliberate strategic act, not as casual play behavior.

### Geological Risk Disclosure

When a player purchases Development Rights, the zone's geological stability score is displayed explicitly before purchase confirmation. This score reflects:
- Proximity to active fault lines in the tectonic simulation
- Historical frequency of tectonic events in the zone
- Current precursor event status (if a geological event is building, this is visible)

Players who build in high-risk zones are making an informed risk/reward tradeoff. Geological volatility zones offer richer resources and lower land costs. They also carry higher structural loss risk. The game does not obscure this.

---

## 7. New Player First 30 Minutes (Varek Delta Default Start)

### Design Principles

1. The player arrives in a world that is already in motion — they do not start at the beginning of anything
2. Systems teach through interaction, not tutorial boxes
3. The player makes a choice with genuine faction consequence before minute 30
4. Every piece of information they receive is delivered through specific world conditions, not generic exposition

### Step-by-Step Walkthrough

**0:00–3:00 — Arrival**

The player is aboard a trade barge approaching the Varek Delta platform city. The game begins mid-travel; no loading screen ceremony. Before the player is active:
- The delta city is visible ahead: layered, industrial, complex
- A departing barge passes — loaded, purposeful, the world already doing business
- Salt crystal formations rise from the shallows below; some are larger than the player character

No tutorial box. The NPC ferryman speaks without prompting: something local and specific — the north channel has been blocked by sandbar shift, merchants are frustrated, work is available at the Factor's post. This is NPC civilizational memory made tangible in the first seconds: the ferryman speaks to current conditions.

**3:00–7:00 — Disembarkation and First Task**

At the dock, a Varekian factor has three tasks posted:
- Short-haul delivery (teaches movement, basic economy)
- Survey request (a merchant wants information on a new sandbar formation — teaches the Read phase)
- Flood repair assistance (teaches environmental hazards)

Alongside the task board, a public notice board shows the last three Historical Ledger entries for the Delta region. One is relevant to something visible in the environment — the player can see the consequence of a logged event with their own eyes. The world has a history; they have arrived in the middle of it.

There is no faction lock at this point.

**7:00–15:00 — First Task Execution**

If the player takes the delivery task: they carry a package two platforms over. Along the route:
- Navigation tutorial happens through movement (no tooltip)
- A salt crystal node on a platform edge can be examined: the game returns a geological observation ("The crystal formed at the boundary where fresh river water meets tidal intrusion — this zone has been tidal for at least a decade") — world information through interaction, not a pop-up
- An NPC conversation about a missing fishing boat is audible in passing — a hook the player can investigate now or return to later
- The receiving merchant's thank-you references the north channel blockage — NPC awareness of current world conditions, not a scripted generic response

**15:00–22:00 — The First Faction Tension**

After the task, the player encounters a Deepwalker geological surveyor on the platform — he has been hired by the Compact for a survey job but has his own interest. He mentions the cave cavity visible beneath the platform district's stone foundations. The Compact plans to drain it for salt extraction. The Deepwalkers oppose this.

The player is not asked to choose sides. They are shown that factions have real, incompatible interests about something physically present in the environment they can see. This is the first faction tension moment — planted here as information, not as a choice yet.

**22:00–30:00 — First Consequential Choice**

The factor sends a follow-up: a saltcrystal formation to the east is being approached by a Tide Compact scout party. The Compact wants the player to reach it first and place a Claim Stake. In return, they will offer a formal faction affiliation contract.

**The player's four options:**

1. **Stake for the Varekian Compact**: the scouts return to their ship empty-handed. Compact affiliation begins. The scouts' failure may register in the Ledger if it is significant enough.

2. **Approach the Tide Compact scouts instead**: they are surprised and pleased. A counter-affiliation offer is made. The Compact factor notes the player chose not to help and adjusts accordingly.

3. **Stake for yourself with no faction flag**: you acquire the salt resource but earn minor negative Varekian reputation. You remain unaffiliated. This is viable.

4. **Decline to engage**: return to the factor without having gone. Inform them of the situation. They note your caution and remain neutral toward you. Affiliation decision deferred. This is valid — there is no mechanical pressure to affiliate immediately.

**By minute 30, without a single tutorial box, the player has:**
- Experienced a world already in motion before and after their session
- Interacted with NPC dialogue responsive to current world conditions
- Learned the Claim Stake mechanic through performing it (or chosen not to)
- Witnessed faction tension about a physical object in the environment
- Made a choice with visible, faction-legible consequence
- Received a planted hook (the underground cavity) discoverable only by having paid attention

---

## 8. Burn-Out and Exploitation Mitigation

### Risk 1: Geographic Control Monopoly

**Failure mode:** A large organized guild dominates all critical resource geography, making the game economically inviable for other players. (The EVE Null-Sec problem, amplified because geography matters more here than in any comparable game.)

**Mitigation:**

| Mitigation | Mechanism |
|---|---|
| Redundant resource distribution | No resource type has fewer than 3 distinct geographic sources in the core world. Controlling all sources simultaneously is a Ledger-level event — visible to the entire server |
| Geological churn | Tectonic events shift resource geography. Controlling geography is a temporary advantage, not permanent ownership of a static asset |
| Claim Stake active defense requirement | High-value stakes that go undefended in contested zones for 12 hours automatically enter Contention. You cannot hold everything without presence |
| Anti-monopoly faction response | If a single entity controls resources above a regional threshold, opposing factions receive a Resistance Event bonus — the Ledger broadcasts the control situation and awards bonus rewards to players who successfully contest it. The world pushes back against monopoly |

### Risk 2: Resource Node Depletion Misery

**Failure mode:** Casual players who log in infrequently find all resource nodes depleted by more active players. Unable to progress crafting. Burn-out from "arriving after the party ended."

**Mitigation:**

| Mitigation | Mechanism |
|---|---|
| Common Ground guarantee | Every zone has designated Common Ground areas with session-respawning lower-yield nodes. Casual players always have access to basic resources |
| Depth-scaled access | Highest-yield nodes require discipline depth and exploration to locate. Casual players get reliable modest supplies; dedicated gatherers earn access to exceptional supplies proportional to their investment |
| Dynamic respawn rate | Tectonically active zones regenerate faster. Reading/Resonance players can identify and publish high-respawn zones — casual players benefit from the community's geological knowledge |
| Market access | A player unable to gather can always buy. The trade system distributes materials from high-production players to lower-access players via market infrastructure |

### Risk 3: Tectonic Events as Involuntary Character Setback

**Failure mode:** A major geological event destroys a player's territory without warning. They return from a break to find their settlement in ruins. They quit. (The "punishing randomness" failure mode.)

**Mitigation:**

| Mitigation | Mechanism |
|---|---|
| Mandatory precursor window | No major tectonic event fires without a minimum 7-day observable precursor window. Players who pay attention have time to prepare, evacuate, fortify, or accept the risk |
| Geological insurance structures | Deepwalker-knowledge geological dampening installations provide tectonic protection for territories. Not foolproof, but meaningful counterplay. Creates faction interdependence |
| Ruin value preservation | Destroyed structures become ruins with salvage value and historical significance. Loss is painful but not erasure — the Legacy record of the structure persists |
| Geological stability disclosure at purchase | Development Rights purchases display the zone's geological stability score before commitment. High-risk zones offer high resource rewards at explicit risk |
| Partial simulation transparency | The tectonic pressure simulation is partially legible to Reading and Resonance discipline players, who can publish forecasts. Players can know the risk is building |

---

## Open Questions for GDD Formalization

The following items require additional design work before the GDD Writer can formalize them into full specifications:

1. **Contention Event mechanic**: When a Claim Stake is challenged, what is the specific resolution mechanic? Options include: PvP combat (most dramatic, may favor military archetypes exclusively), timed gathering race (inclusive, favors all archetypes), diplomatic/bidding resolution (favors economy players). Recommendation: a tiered system where the contesting party can choose resolution type but the defending party gets home-territory advantage in all modes. Requires System Designer specification.

2. **Historical Ledger significance threshold**: What magnitude of action qualifies a player action as a Ledger entry? This threshold determines the entire feel of civilizational memory. Too low floods the Ledger with trivialities. Too high makes most player actions invisible at the civilizational scale. Requires System Designer quantification.

3. **Strata depth power calibration**: The combat power differential between Surface and Core Understanding in each discipline must be precisely calibrated. The design intent is that the gap is real but not so wide that veterans are untouchable. Requires balance specification by the System Designer.

4. **Terrain Stance technical feasibility at 500+ players**: The combat system's per-zone geological state tracking must be validated against server-side performance at scale. The design describes the system as zone-event-tick-managed, not per-frame — this is a feasibility assumption that requires Tech Architect validation.

5. **Decay timer calibration**: The 30/60/90/180-day abandonment decay timeline is a first estimate. Appropriate timers may vary by structure scale (a player-owned shack versus a faction fortification) and historical significance (a structure with Ledger entries versus one with none). Requires iteration.

---

## System Dependencies

This document's mechanics depend on or interact with the following systems not yet designed:

| System | Dependency Type | Notes |
|---|---|---|
| Faction Historical Ledger | Core dependency | Mechanic Design assumes Ledger exists and is queryable; Ledger design not yet formalized |
| Tectonic Simulation Model | Core dependency | Economy loop, land ownership, and geological events all depend on a server-side tectonic state; implementation not yet specified |
| Procedural Generation System | Interaction | Demographic trigger in World Primer feeds into this loop; generation rules established but generation mechanic not yet designed |
| NPC Behavior System | Interaction | NPCs must reflect faction Ledger state in dialogue and patrol behavior; NPC behavior design not yet formalized |
| Anchor Installation System | Interaction | Founder installations referenced in progression, economy, and combat; installation mechanics not yet designed |

---

*This document represents the core gameplay loop as designed in Mechanic Designer Session 001. It is intended as input for the GDD Writer (AGT-003) to formalize into complete Game Design Document sections. All section headings follow the GDD document standard defined in docs/game-design/README.md.*
