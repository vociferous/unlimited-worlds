# Unlimited Worlds — Game Design Document v0.1

**Document type:** Master GDD — Phase 0 Authoritative Reference  
**Version:** 0.1  
**Date:** 2026-05-31  
**Author:** AGT-003 GDD Writer  
**Source sessions:** AGT-001 World Architect Session 001, AGT-002 Mechanic Designer Session 001  
**Status:** Authoritative for Phase 0; input document for Phase 1 scoping  
**Review required from:** System Designer (balance), Tech Architect (feasibility flags noted inline)

---

## Table of Contents

1. [Game Overview](#1-game-overview)
2. [Core Gameplay Loop](#2-core-gameplay-loop)
3. [Player Progression](#3-player-progression)
4. [Combat System](#4-combat-system)
5. [Economy System](#5-economy-system)
6. [Land and Territory System](#6-land-and-territory-system)
7. [Faction System](#7-faction-system)
8. [New Player Experience](#8-new-player-experience)
9. [Open Questions Register](#9-open-questions-register)
10. [System Dependencies Map](#10-system-dependencies-map)

---

## 1. Game Overview

### Vision Statement

Unlimited Worlds is a massively multiplayer online role-playing game set in Dern Varath, a world whose geology is its metaphysics and whose history is recorded in stone. The central premise: the game world is alive, mutable, and permanently scarred by what players do in it. No two players experience the same Dern. Player actions reshape geography, drive economic conditions, and enter civilizational memory. The world persists and accumulates consequence whether or not any individual player is logged in.

The player's goal is not to defeat a villain or reach the end of a story. It is to decide the shape of the world.

### Core Pillars

Each pillar is defined with a measurable criterion so that design decisions can be evaluated against it.

| Pillar | Definition | Measurable Criterion |
|---|---|---|
| **Living World** | The world changes state in response to player actions and internal simulation ticks — geography, faction power, and economic conditions shift on observable timescales | At least one zone-level world state change observable per real-world week per active server region |
| **True Persistence** | Player actions leave traceable, non-resetting marks in the game world that outlast any individual session | Player-triggered events persist in the faction Historical Ledger for a minimum of 30 real-world days before Legend Layer decay; terrain alterations and Claim Stakes persist indefinitely |
| **Emergent Narrative** | Stories arise from the interaction of player choices and world systems, not from scripted quest chains alone | At least 30% of faction Historical Ledger entries in any given week are player-triggered, not developer-scripted |
| **Boundless Scale** | The world expands procedurally via internal logic, not developer patch cycles | New regions can be generated without developer content updates, triggered by tectonic, demographic, or catastrophe thresholds (see Section 7.3) |
| **Deep Economy** | Resource scarcity, geographic price differentials, and player-controlled supply chains create meaningful economic decisions with real trade-offs | No single item's supply chain is executable within a single biome at Tier 3 crafting; all faction capital market prices are player-supply-influenced |

### Genre and Platform Target

- **Genre:** MMORPG, open-world, sandbox-adjacent
- **Platform target:** PC primary (Windows/Linux); console evaluation deferred to Phase 3
- **Player count targets:**
  - Phase 1 prototype: 50 concurrent players per zone
  - Phase 2 vertical slice: 100+ concurrent players per zone
  - Phase 3 alpha: 500 concurrent players per zone (design ceiling for all mechanics in this document)
  - Phase 4 beta: 10,000+ concurrent players across multiple servers
- **Session target:** 45–90 minutes; designed to be meaningful in under 60 minutes without mandatory longer commitment

---

## 2. Core Gameplay Loop

### Overview

The core loop is the repeating unit of play. Every player archetype — combat, gatherer, crafter, explorer, faction operative — performs the same three-phase cycle. Activities differ by archetype; the structure does not.

**The loop in one sentence:** The player reads the world's current geological and political state, takes an action that changes it, and leaves a traceable mark — then reads again to see how the world responded.

### 2.1 Phase 1: Read

**Purpose:** To give players the information they need to make meaningful decisions, and to reward the skill of reading the world over purely reactive play.

**Target duration:** 1–3 minutes per cycle.

**Inputs:**
- Zone geological indicator state (visual: crystal growth patterns, cracking surfaces, waterline changes; auditory: subsonic rumble, sulfur concentration, dripping water rates)
- Faction Historical Ledger (public display in town centers; accessible via faction UI panel; shows last N significant events for the region)
- NPC behavioral patterns (patrol density, merchant inventory availability, dialogue content referencing current events)
- Resource field state (visible depletion status of nodes; Claim Stake markers)
- Player's current discipline depth (determines how much information the above inputs yield — see Section 3)

**Rules:**

1. Every zone maintains a queryable geological state descriptor updated on zone event ticks (not per-frame). This descriptor is the basis for all Read-phase outputs.
2. A Surface Understanding player (Strata 1–10) perceives basic geological indicators: a cave entrance looks unusual, a salt flat looks active.
3. A Formation Understanding player (Strata 11–25) perceives compositional signals: the strata above a cave entrance predict a rare mineral upwelling inside.
4. A Mantle Understanding player (Strata 26–40) perceives process signals: the upwelling matches a Founder-era resonance signature, indicating an Anchor installation in proximity.
5. A Core Understanding player (Strata 41–50) perceives predictive signals: the resonance signature indicates the installation type, activation status, and approximate depth.
6. The faction Historical Ledger is always readable by any player; no discipline depth is required. Depth affects geological interpretation of events in the Ledger, not access to it.
7. The Read phase is never mandatory — a player can proceed directly to Act — but players who skip the Read phase forgo discipline-depth bonuses on their Act phase output.

**Outputs:**
- Player decision: which activity to pursue and by what method
- Situational awareness bonus: 5–20% efficiency modifier on subsequent Act phase, scaled by discipline depth and quality of environmental signals read (exact tuning: System Designer sign-off required)

**Edge Cases:**
- *Player in a newly generated procedural region:* No Historical Ledger entries exist for the zone yet. All players begin on equal Read-phase footing — no one has depth advantage in a zone with no geological history. This is intentional.
- *Player with no discipline investment (Strata 1 in all disciplines):* Read phase yields only basic visual indicators. This is the floor, not a lock-out. All players can still Act; they just forgo information bonuses.
- *Conflicting signals (tectonic precursor event + faction conflict):* Multiple active signals in the same zone are displayed simultaneously. Resolving which signal is most actionable is a player skill judgment call, not a system-driven recommendation.

---

### 2.2 Phase 2: Act

**Purpose:** To give players a mechanically substantive activity that changes world state. Every archetype's Act must require decisions; passive waiting is not a valid Act.

**Target duration:** 5–10 minutes per cycle.

**Inputs:**
- World state as read in Phase 1
- Player's current discipline depth (affects available extraction methods, combat stances, exploration bonuses)
- Faction affiliation and Civilizational Contribution Score (affects which zones are accessible, what faction resources are available)
- Other players' current activity in the zone (creates competition, cooperation, or conflict opportunities)

**Act types by archetype:**

| Archetype | Primary Act | Required Decisions |
|---|---|---|
| Combat | Engage contested zone; defend or take territory | Terrain Stance selection; ability sequencing; engagement timing |
| Gatherer | Extract from resource node using discipline techniques | Survey vs. skip; extraction method (Blast/Precision/Standard); yield vs. terrain-preservation trade-off |
| Crafter | Transform raw materials into refined goods or structures | Material combination (origin geology affects output properties); tier selection |
| Explorer | Move into unmapped or procedurally generated territory; document findings | Documentation depth (quick survey vs. full geological record); which formations to prioritize |
| Faction operative | Execute a mission at faction-Ledger scale | Mission type selection; risk/reward calibration; ally coordination |

**Rules:**

1. Every Act phase must produce at least one of the following: (a) a resource in the player's inventory, (b) a territory state change, (c) a cartographic update, or (d) a faction metric change. Acts that produce none of these are non-qualifying Acts and do not advance the loop.
2. No Act phase is fully automated. Extraction requires method choice. Combat requires stance activation. Exploration requires documentation decisions. Automated or AFK gameplay does not satisfy the loop.
3. The Act phase output scales with the quality of the preceding Read phase. A player who read the zone's geological state correctly before extracting a node receives the information bonus on extraction yield.
4. Act phase activities that meet the faction Historical Ledger significance threshold (see Open Questions Register, OQ-002) additionally trigger a Mark-phase Ledger entry.

**Outputs:**
- Tangible result: resources, damage dealt, territory changed, information recorded, structures built or destroyed
- World-state delta: the input for Phase 3 (Mark)

**Edge Cases:**
- *Two players simultaneously attempting to extract the same node:* Simultaneous extraction proceeds at reduced yield for both players, proportional to the node's remaining capacity divided by the number of active extractors. Depletion is shared. First-finder bonus is not affected (it was awarded at discovery, not during extraction sessions).
- *Act phase interrupted by zone-level geological event:* The event takes priority. If the player's Act was in progress, partial output is preserved (e.g., partial extraction yield). The zone event is then processed before the player re-enters Act.
- *Player attempts an Act that requires a higher Strata than they currently possess:* The Act is blocked with a world-legible reason (e.g., "You do not have the geological depth to interface with this formation"). The player is directed toward the type of world engagement that would advance their Strata.

---

### 2.3 Phase 3: Mark

**Purpose:** To close the feedback loop by making player actions visible and persistent in the world. The Mark phase is the mechanism by which True Persistence is delivered at the core loop level.

**Target duration:** 30 seconds–2 minutes (largely automatic; player confirms or observes).

**Inputs:**
- Act phase output (the world-state delta produced by the Act)
- Zone state at time of Mark
- Player's faction affiliation and Ledger significance score for the Act performed
- Whether the Act met the Ledger significance threshold

**Rules:**

1. Every completing Act phase triggers a Mark phase. There are no Acts without Marks.
2. Mark types are assigned by the nature of the Act:
   - Resource extraction → node depletion marker (visible to all players; shows remaining yield percentage)
   - Claim Stake placement → visible world marker (flag in world, icon on zone map)
   - Faction-Ledger-eligible Act → Ledger entry created (details in Section 7.2)
   - Territory change → zone control indicator updated
   - Exploration → cartographic update added to shared world map with player attribution
   - Anchor installation interaction, terrain destruction, major geological event participation → geological imprint (permanent zone state change)
3. Marks are visible to other players immediately upon creation. There is no delay window during which a Mark is private.
4. The Mark phase cannot be suppressed or skipped by the player. Choosing not to participate in a faction-eligible Act does not generate a Ledger entry; but extraction node depletion, cartographic updates, and Claim Stake placements are automatically recorded.
5. Marks decay only through defined game systems:
   - Node depletion recovers on geological regeneration timescales
   - Claim Stakes expire after 72 hours unless renewed
   - Ledger entries age into the Legend Layer after N significant events push them out (see Section 7.2)
   - Geological imprints are permanent

**Outputs:**
- Updated world state (visible to all zone participants and on the world map)
- Ledger entry (if significance threshold met)
- Player's Geological Legacy update (if Act was of Legacy-qualifying significance)
- Input for next cycle's Read phase (the player can immediately observe what their Act changed)

**Edge Cases:**
- *Player logs out before Mark phase completes:* The Act phase output is committed to the world state regardless. A player cannot undo a Mark by logging out.
- *Act produces a Ledger entry for a faction the player is not affiliated with:* The entry still occurs. A Tide Compact player who destroys an Ashbound fortification produces an entry in the Ashbound Ledger (noting the loss) and potentially one in the Tide Compact Ledger (noting the gain). Both are created.
- *Simultaneous Marks from multiple players producing contradictory zone states:* Zone state changes are processed in order of completion timestamp. Last Mark wins for contested state changes. Simultaneous contested territory captures are resolved by a tie-breaker: the player with the higher Civilizational Contribution Score in the relevant faction wins. If tied, the occupying player wins (defender advantage).

---

### 2.4 Session Loop (~1 Hour)

**Purpose:** To give each play session meaning beyond the individual core cycle — the sense that the player changed something at world scale.

**Structure:** 4–6 core loop cycles, plus three meta-activities per session:

| Meta-Activity | Definition | Minimum Qualifying Threshold |
|---|---|---|
| One faction-relevant action | An Act that touches the faction Historical Ledger or moves a faction metric | Delivering significant mineral quantity to faction trade post; completing a faction-issued mission; winning a contested zone skirmish; performing a faction-requested survey |
| One exploration or intelligence action | Discovering something new or gathering intelligence for the next session's Read phase | Documenting a new resource node; recording a geological anomaly; reading a Ledger change and noting its map implication; surveying a procedurally generated zone for the first time |
| One economic transaction | Participating in the trade economy in a material way | Selling crafted goods at a regional market; buying materials from another player; contributing resources to a faction supply chain |

**The session ends with evidence of external change.** The world is not identical to how it was when the player logged in. At least one of the following is true: a territory marker has moved, a Ledger has been updated, a node has been depleted, a map has a new entry.

---

### 2.5 Weekly Loop

**Purpose:** To create the perception of civilizational time — the sense that the world is moving on a longer arc that rewards consistent engagement without punishing casual players.

Three cycles run concurrently at the weekly scale:

**Faction event cycle (3–5 days):** Major faction events — territorial disputes, geological anomaly discoveries, resource crises, political negotiations — fire on a 3–5 day real-world cycle. Players who are present during an active event experience the world under pressure. Those who miss it return to a world where the outcome has been recorded in the Ledger. The Ledger creates the "newspaper effect": players returning after a few days feel compelled to read what changed.

**Geological cycle (7–10 days):** Tectonic precursor events — tremors reported by NPCs, anomalous tidal behavior, unusual NPC migration, new geological indicator readings — are observable over a 7–10 day window before a generation or transformation event fires. Players who are present during this window piece together the forecast. Players who miss it encounter the outcome. Reading-discipline players can publish geological forecasts that other players act on. Forecasting is a collaborative activity.

**Market cycle (5–7 days):** Resource supply/demand curves resolve on weekly timescales. A depleted node creates a price spike within 48–72 hours in nearby markets. A new vein discovery stabilizes prices within 72–96 hours. Players managing economic positions need weekly attention but not daily mandatory sessions.

---

### 2.6 Long-Term Arc: The Geological Legacy System

**Purpose:** To give players a non-resettable record of long-term world impact that provides access and meaning without creating insurmountable power gaps against newer players.

**Design principle:** Legacy is not power. It is access and meaning.

**Legacy components:**

| Component | Description | Persistence |
|---|---|---|
| Territorial Imprint | Land the player has claimed, developed, defended, or destroyed | Persists until another player changes it |
| Faction Ledger Entries | Events the player triggered that entered civilizational memory | Active until Legend Layer decay; then persists indefinitely as legend text |
| Geological Marks | Resource nodes discovered, terrain altered, Anchor installations activated or destroyed | Permanent changes to world geography |
| Civilizational Contribution Score (CCS) | Faction-specific measure of contribution to faction position | Unlocks access to higher-tier faction content; does not increase raw combat power |

**Rules:**

1. A player with a 2-year Legacy is not twice as powerful in combat as a new player. The Strata system compresses combat power differentials (see Section 3.4). Legacy advantages are breadth of access, historical context, and Ledger significance — not raw power multiplication.
2. New players in newly generated procedural regions begin on equal Legacy footing with veterans; no one has established marks in a zone that did not exist until last week.
3. Tectonic disruption events in established zones partially reset veteran contextual advantage: the geological state they mastered has changed. New and veteran players both must Re-Read.
4. A player's Geological Legacy record persists indefinitely, including after account inactivity. The world records that they were here.

---

## 3. Player Progression

### Overview

Character progression is organized around four **Geological Disciplines** — domains of understanding of the Dern's geological mechanics. Disciplines are not classes. They define what the player understands about the world and therefore what they can do in it.

### 3.1 The Four Disciplines

**Resonance**

- **Purpose:** Understanding and manipulation of geological resonance — the deep language of the Dern and the operating language of Founder technology
- **Primary faction affiliation:** Deepwalker Compact (not locked; any player can develop Resonance)
- **Combat role:** Support and battlefield control; the discipline most capable of reading and disrupting enemy Terrain Stances
- **Economic role:** Founder installation investigation; rare material identification; geological forecasting; node quality assessment without survey tools
- **Unique capability:** The only discipline with full Anchor Network interface capability at advanced Strata depths. Mantle-level Resonance is required to activate a partial installation; Core-level Resonance may be required for complete installations

**Shaping**

- **Purpose:** Forceful geological manipulation — volcanics, seismic events, terrain modification
- **Primary faction affiliation:** The Ashbound
- **Combat role:** Offensive devastation and terrain destruction; the highest raw-damage combat discipline
- **Economic role:** Mine development, terrain clearing, large-scale construction preparation, fortification development and destruction
- **Unique capability:** The only discipline capable of permanent, irreversible terrain alteration. Formation-level Shaping minimum required; Mantle-level for major terrain alteration

**Reading**

- **Purpose:** Geological intelligence — extracting information from terrain, predicting changes, exploiting commercial opportunity
- **Primary faction affiliation:** Varekian Compact
- **Combat role:** Intelligence and tactical support; Reading practitioners provide the best pre-combat geological situation assessments
- **Economic role:** Resource forecasting, market positioning, geological survey-for-hire, first-mover identification of new resource opportunities
- **Unique capability:** The highest yield from geological observation. A Core Reading practitioner extracts more actionable information from the same environment than any other discipline

**Charting**

- **Purpose:** Geographical mastery — moving through, documenting, and claiming new territory
- **Primary faction affiliation:** Tide Compact
- **Combat role:** Scouting and mobile skirmishing; the highest-mobility combat discipline
- **Economic role:** Exploration, first-finder bonuses, cartographic trade goods, salvage of procedurally generated zones and drowned ruins
- **Unique capability:** Highest movement efficiency in unmapped territory; access to Tide Compact's procedural frontier infrastructure; first-mover claim advantages in newly generated regions

### 3.2 Cross-Discipline Training

1. Players choose a primary discipline at character creation, connected to their starting faction's expertise. This is the discipline that governs their starting ability set and initial Strata accumulation rate.
2. Players can develop secondary disciplines over time through world engagement. Secondary disciplines have no maximum Strata ceiling — full Core Understanding in a secondary discipline is achievable but requires proportionally greater world engagement.
3. Cross-training produces meaningfully distinct archetypes, not merely additive bonuses:
   - Resonance primary + Reading secondary: can both interface with Founder technology AND forecast geological change — the closest living equivalent to a Founder scholar
   - Shaping primary + Charting secondary: can destroy terrain AND efficiently move through new geography — a mobile terrain-warfare specialist
   - Reading primary + Resonance secondary: can forecast AND partially interface with Anchor technology — an economic intelligence specialist with Founder tech access
4. Cross-training is meaningful but never replaces depth in the primary discipline. A primary Resonance practitioner at Mantle-level outperforms a secondary Resonance practitioner at Mantle-level in precision and efficiency of Founder tech interaction.

### 3.3 Strata Depth

Progression within a discipline is measured in **Strata** — a geological metaphor for depth of understanding.

| Strata Range | Geological Name | Equivalent Role |
|---|---|---|
| 1–10 | Surface Understanding | Novice |
| 11–25 | Formation Understanding | Intermediate |
| 26–40 | Mantle Understanding | Advanced |
| 41–50 | Core Understanding | Expert |

Core Understanding (41–50) represents knowledge equivalent to Founder geological mastery. Fewer than 5% of the player population is expected to reach Core in any discipline during the first year. Reaching Core in any discipline is a world-legible achievement — the Historical Ledger will record it.

### 3.4 Progression Inputs

Progression comes from engagement with the world, not from accumulated kills:

1. **Geological feature engagement:** Interacting with geological features relevant to your discipline (Resonance practitioners gain Strata from Founder installation proximity and interface attempts; Shaping practitioners gain Strata from terrain modification acts; Reading practitioners gain Strata from geological survey acts; Charting practitioners gain Strata from documenting new territory)
2. **Faction Ledger events:** Participating in Acts that enter the faction Historical Ledger contributes discipline Strata to all participants, scaled by the significance of the event
3. **Discovery bonus:** The first player to document a new geological formation receives a discipline Strata bonus
4. **Mentorship:** Teaching a player at lower Strata depth (confirmed through a shared in-world activity) awards modest Strata progression to the teaching player

### 3.5 World-Gated Depth Progression

Advancing between Strata tiers requires direct engagement with world locations, not merely accumulated activity:

| Tier Transition | World Gate Requirement |
|---|---|
| Surface → Formation (Strata 10→11) | Must have directly engaged with a Formation-depth geological feature (accessible in all four starting biomes) |
| Formation → Mantle (Strata 25→26) | Must have directly engaged with a Mantle-depth geological feature in the world — an actual underground or deep-geological location requiring physical access |
| Mantle → Core (Strata 40→41) | Must have directly engaged with a Core-depth geological formation — which in practice means a functioning or partially-functioning Anchor Network installation |

This prevents purely mechanical advancement through repetition. Reaching Mantle requires going somewhere. Reaching Core requires finding and engaging with Founder technology.

### 3.6 New Player Competitiveness

1. Combat power differential between Strata is compressed by design. A Surface-level Shaper is not 10 times less effective in combat than a Core-level Shaper. The difference is breadth of capability, precision, and access — not a raw power multiplier.
2. New players in newly generated procedural regions begin on equal geological footing with veterans. A zone generated last week has no incumbent experts.
3. Tectonic disruption events in established zones partially reset veteran contextual advantage. Veterans whose knowledge was built on the previous geological state must Re-Read alongside new players.

**Sign-off required:** System Designer must specify the exact combat power differential between Strata tiers (see OQ-003).

---

## 4. Combat System

### Overview

Combat in Unlimited Worlds uses a **modified hybrid targeting system** layered with a **Terrain Stance system** that introduces biome-specific geological combat modifiers. The hybrid approach was selected over pure action combat (infeasible at 500+ players per zone; accessibility concerns) and pure tab-target (does not express the geological setting).

### 4.1 Hybrid Targeting Base

**System classification:** Positional awareness required (player position and orientation affect ability effectiveness) + skill-slot ability management (no auto-attack) + soft targeting (abilities can hit targets in a cone/area without precise cursor aim, but positional optimization is rewarded).

**Faction combat identities:**

| Faction | Combat Identity | Primary Mechanical Role |
|---|---|---|
| Varekian Compact | Battlefield control and redirection | Crowd control, terrain manipulation, debuff |
| Ashbound | Aggressive overwhelming force | Offensive damage, terrain destruction |
| Deepwalkers | Patience and attrition | Environment exploitation, disorientation, trap mechanics |
| Tide Compact | Speed and adaptability | Flanking, scouting, controlled withdrawal |

### 4.2 The Terrain Stance System

**Purpose:** To make combat mechanically distinct in different geological environments, expressing the world's core identity in the game's primary conflict system.

**Inputs:**
- Zone geological state descriptor (rock type, mineral composition, moisture content, seismic activity level)
- Player's discipline depth in the relevant faction skill
- Current terrain sub-type in the player's position (obsidian floor, salt flat, underground karst, coastal zone, etc.)

**Rules:**

1. Every biome and sub-region has a geological state updated on zone event ticks (not per-frame). This state is the basis for available Terrain Stances.
2. Players with relevant faction discipline depth can read the zone's geological state and adopt a Terrain Stance — a combat modifier that reflects deliberate use of the environment's geological character.
3. Terrain Stance activation requires a 3-second channel. During this channel, the player is briefly more vulnerable to interruption. This prevents Stances from being cost-free.
4. Only one Terrain Stance can be active at a time. Switching stances requires re-channeling.
5. Terrain Stances are faction-knowledge-gated: a player must have the relevant faction relationship (not necessarily full affiliation; neutral reputation is sufficient) and minimum Strata depth to activate a given Stance.
6. A player fighting outside their Stance's optimal environment (e.g., using Ashbound Volcanic Stance on a coastal zone) receives no Stance benefits and no Stance penalties — the Stance simply does not activate.

**Terrain Stance specifications:**

**Ashbound Volcanic Stance** (activates on obsidian floor surfaces; Scorch Plateau and volcanic sub-zones):
- Grants: heat damage rider on physical abilities; access to magma vent eruption triggers (environmental attack mechanic activated by accumulated heat damage thresholds)
- Costs: reduced movement speed (terrain is dangerous to traverse quickly); increased vulnerability to cold-type effects
- Minimum depth: Formation Understanding (Shaping)

**Varekian Salt Attunement** (activates on crystalline salt terrain; Varek Delta salt flat sub-zones):
- Grants: crystal fragmentation creates area-denial zones when struck by abilities; high-ground position advantage on elevated salt formations; salt storm trigger if cumulative formation damage exceeds zone threshold
- Costs: movement patterns are partially telegraphed (salt crystal terrain is visually distinctive, making flanking attempts more visible)
- Minimum depth: Formation Understanding (Reading)

**Deepwalker Deep Sense** (activates underground or in cave-adjacent environments; Deepwalker Karst and underground sub-zones):
- Grants: darkness exploitation (reduced enemy detection range for Deepwalker-side in low-light zones); sound-based positioning awareness (audio cues indicate enemy movement before visual contact); collapse trap mechanic (triggering ceiling instability in geologically weak sections)
- Costs: weaker in open-air environments; collapse traps are slow to set up and require Resonance depth to assess structural weakness accurately
- Minimum depth: Formation Understanding (Resonance)

**Tide Compact Open Water Stance** (activates near water in coastal/maritime sub-zones):
- Grants: flanking speed bonus when attacking from a water-adjacent position; weather exploitation (increased damage during active storm events); withdrawal bonus (reduced cast interruption when breaking combat toward water)
- Costs: only operates near water; no terrain-denial capability; weather exploitation requires active storm event (intermittent availability)
- Minimum depth: Formation Understanding (Charting)

### 4.3 Large-Scale Combat (500+ Players)

At 500+ player scale, individual Terrain Stance activations aggregate into zone-level effects:

1. Mass Ashbound combat activity in a volcanic zone can trigger a server-resolved geological event (eruption event) that affects the entire zone's combat state for a timed period. The event is pre-announced by escalating geological indicators. It does not fire without warning.
2. Mass Varekian salt manipulation can trigger a salt storm zone event, affecting visibility and movement for all participants in the zone.
3. Zone-level events are computed server-side on zone event ticks. They are not calculated per-player per-frame. Individual combat resolution (hit/miss/ability effects) uses standard hybrid calculation.

**Technical feasibility note — sign-off required:** The Terrain Stance system's per-zone geological state tracking must be validated against server-side performance at 500+ players per zone. The design specifies zone-event-tick management (not per-frame calculation) specifically to address this. This is a feasibility assumption that requires Tech Architect validation before Phase 1 begins. See OQ-004.

### 4.4 Edge Cases

- *Player attempts Terrain Stance in a zone undergoing a geological event:* Stance activation is blocked during active zone events (the geological state is in flux). This is communicated via an environmental indicator (the ground is shaking; the stance cannot be held). Players fight in base mode during zone events.
- *Two opposing players with the same Terrain Stance (e.g., both Ashbound in a volcanic zone):* The Stance benefits apply to both sides equally. The zone-level geological event triggers apply regardless of which faction initiated the threshold. This is intentional — the zone becomes dangerous for everyone when volcanic activity peaks.
- *Player with no faction affiliation attempts to use a Terrain Stance:* Unaffiliated players cannot activate Terrain Stances. They fight in base hybrid mode. This is an intentional incentive for faction affiliation that is introduced visually in the first 30 minutes (see Section 8).

---

## 5. Economy System

### Overview

The Unlimited Worlds economy is a geography-grounded supply chain: resources are extracted from specific geological locations, transformed through geological crafting techniques, and traded across a physically located market network. Every stage expresses the geological theme. The primary anti-inflation mechanism is genuine resource scarcity combined with mutable geography — resources move and regenerate on geological timescales, not developer-set respawn timers.

### 5.1 Gathering

**Purpose:** To make resource extraction a skilled activity that rewards geological knowledge and creates persistent world marks.

**Inputs:**
- Zone's resource node state (quantity remaining, geological composition, extraction risk)
- Player's discipline depth (determines available extraction methods and survey capability)
- Claim Stake status on the node (determines extraction priority)

**Rules:**

1. **Survey (Reading discipline):** Before extracting, a player with Reading discipline can survey the formation. Survey output: predicted quality tier, approximate yield, structural risk (will aggressive extraction destabilize the surrounding terrain?), geological characteristics relevant to Tier 2 and Tier 3 crafting use. Players without Reading discipline extract without this information — they receive what the node yields without optimization.
2. **Extraction method:**

| Method | Speed | Yield | Terrain Effect | Discipline Required |
|---|---|---|---|---|
| Blast Extraction | Fast | Moderate | Damages surrounding terrain; reduces total node yield | Shaping, Formation minimum |
| Precision Extraction | Slow | High | Preserves terrain; maximizes node yield | Resonance, Formation minimum |
| Standard Extraction | Medium | Standard | Neutral | None |

3. **Node depletion:** All resource nodes have finite yield. Depletion is visible to other players (node appears partially or fully exhausted). Regeneration rate scales with local geological activity:
   - Tectonically active zones: faster regeneration (new material upwelling from tectonic movement)
   - Stable zones: slower regeneration
   - Magically disrupted zones (Anchor technology misuse): unpredictable regeneration
4. **First-finder bonus:** The first player to discover and document a resource node receives a permanent minor yield bonus (exact percentage: System Designer tuning required) on that node. This is recorded in their Geological Legacy and visible to other players as a discovery attribution marker on the node.
5. **Common Ground guarantee:** Every zone contains designated Common Ground areas. Common Ground nodes fully regenerate once per server day. These nodes have lower maximum yield than deep-field nodes but are never permanently depleted. No player who logs in should be unable to gather because they missed yesterday's session.
6. **Simultaneous extraction:** Multiple players extracting the same node simultaneously share the remaining yield proportionally. All extractors receive their proportional share at their respective extraction method's yield rate.

**Outputs:**
- Raw materials in player inventory, with origin geology metadata attached
- Node depletion mark (visible world state change)
- Discovery Ledger entry if first-find

**Edge Cases:**
- *Player uses Blast Extraction on a Common Ground node:* Blast Extraction yield bonuses do not apply to Common Ground nodes — they are capped at Standard yield to protect the casual access guarantee. The terrain damage effect still applies.
- *Node located in contested territory with multiple Claim Stakes:* The most recently renewed Claim Stake takes extraction priority. Contested multi-stake situations trigger an automatic Contention Event (see Section 6.2).
- *Resource node depleted to 0:* The node marker persists in the world but shows 0% yield. It does not disappear. Its geological composition data remains available to surveyors (who may use it to forecast when regeneration will begin).

---

### 5.2 Crafting

**Purpose:** To make the geographic origin of materials economically meaningful and to create inter-faction resource interdependence at the highest crafting tiers.

**Inputs:**
- Raw materials with origin geology metadata
- Crafting facility tier (available in faction territories and player-built structures)
- Player's discipline depth (determines which crafting tiers are accessible)

**Tier structure:**

**Tier 1 — Raw Processing**
- Definition: Convert extracted materials into workable stock (ore to ingots, mineral formations to powders, biological materials to alchemical bases)
- Requirements: Basic faction infrastructure; no special discipline required
- Output: Standardized stock materials. Origin geology metadata is preserved but does not affect Tier 1 output properties
- Availability: Accessible to any player at any faction trade post or player-constructed basic workshop

**Tier 2 — Geological Crafting**
- Definition: Apply discipline knowledge to produce goods with properties derived from their origin geology
- Requirements: Formation Understanding in any relevant discipline; Tier 2 crafting facility
- Output: Goods with mechanically distinct properties based on origin geology. A blade crafted from Scorch Plateau obsidian has fire-affinity properties (increased fire damage on hit; higher durability in heat environments; reduced durability in cold environments). The same blade crafted from Shatter Coast mineral deposits has salt-corrosion resistance properties. Origin geology is not flavor text — it produces statistically distinct item modifiers.
- Rule: Two items crafted to the same recipe but from different origin geologies are mechanically non-identical. The origin metadata from gathering is the distinguishing factor.

**Tier 3 — Synthesis**
- Definition: Combine materials from two or more distinct geological sources to produce hybrid materials with properties unavailable from either source alone
- Requirements: Mantle Understanding in at least one discipline; access to a Synthesis facility (available only in major faction capital cities or high-development player settlements); materials sourced from at least two distinct biome types
- Output: Hybrid materials with unique property combinations. A Resonance practitioner synthesizing Deepwalker rare minerals with Ashbound volcanic ore produces materials that no single-source process can replicate
- Rule: Synthesis recipes are geological knowledge, not dropped items. They are discoverable through world interaction (specifically, through Resonance and Reading discipline engagement with multi-biome geological formations). The discoverer's name is attributed in the Ledger. The knowledge can be shared, sold, or kept secret — all of which produce distinct social and economic dynamics.
- Design intent: Synthesis is the primary driver of cross-faction resource trade. No faction controls all biome types required for Synthesis. Hostile factions may still trade raw materials because Synthesis economics demand it.

**Outputs:**
- Crafted items with origin-geology properties embedded
- Structure components for player development
- Synthesis materials available only through this process

**Edge Cases:**
- *Player attempts Tier 3 Synthesis with materials from only one biome type:* The recipe is not available. The crafting interface communicates what biome type is missing. This is not obscured.
- *Synthesis recipe discovered by a player who then goes inactive:* The recipe knowledge exists in their Geological Legacy record and in any Ledger entry generated by the discovery. Other players can find the same recipe through the same discovery process — recipe knowledge is not player-locked.

---

### 5.3 Trade and Markets

**Purpose:** To make geographic price differentials a real economic driver, and to make transport a cooperative gameplay layer rather than a menu operation.

**Inputs:**
- Regional supply and demand (player extraction volumes, consumption rates, transport activity)
- Faction capital market state
- Player inventory and Civilizational Contribution Score (affects access to certain faction-restricted goods)

**Market types:**

| Market Type | Liquidity | Price Level | Access |
|---|---|---|---|
| Faction capital markets | High | High (intermediary markup) | Accessible within faction territory and to aligned faction players |
| Regional trade posts | Medium | Regional supply/demand pricing | Accessible to any player who reaches the location |
| Direct player-to-player | Variable | Negotiated directly | No fee; requires finding the counterparty; no location requirement |

**Rules:**

1. **No global auction house.** Markets are physically located. A player in the Deepwalker Karst cannot list an item on the Varekian Capital Market without physically transporting the item to that market (or contracting another player to do so).
2. **Prices reflect regional supply and demand in real time.** Server-side market simulation runs on the market cycle (5–7 day resolution; see Section 2.5). Individual large transactions can move prices within a session.
3. **Transport is a gameplay layer.** Moving goods from production zone to consumption market is an economic activity with:
   - Reward: price differential (the production-zone price minus the consumption-zone price)
   - Risk: interdiction by other players in contested zones; geological hazard in tectonically active zones; time and distance cost
4. **High-value cargo transport:** Player-organized convoys for high-value transport are a cooperative social mechanic. Solo transport of low-value goods is safe in most non-contested zones. Contested territory transport is a conscious risk/reward decision.
5. **PvP flagging for transport zones must be clear and consensual.** Players carrying high-value cargo in contested zones are automatically PvP-flagged and visible on the zone map as a cargo indicator. Low-value transport in non-contested zones is PvP-protected. The threshold between "low-value" and "high-value" for flagging purposes requires System Designer specification (see OQ-006, flagged for design).

**Outputs:**
- Resource flow from extraction zones to consumption zones
- Regional price signals that inform player economic decisions
- Economic interdependence between factions (because Synthesis requires multi-biome materials)

**Edge Cases:**
- *Player transports goods through a zone that shifts geological state mid-transport (e.g., a tectonic event fires):* Goods in transit are not automatically destroyed. The player must navigate the geological hazard or find an alternate route. If the player's character is incapacitated by the event, goods drop as loot in the world and can be retrieved or contested.
- *Faction capital market prices crash due to coordinated player sell-off:* The market simulation absorbs this over the market cycle. There is no price floor set by the developer. Coordinated market manipulation is a legal player activity and a form of faction warfare. The Ledger records significant market events (exact significance threshold: see OQ-002).

---

## 6. Land and Territory System

### Overview

The land ownership system operates on three tiers, each with distinct mechanics and persistence levels. The foundational principle: no form of ownership can prevent any player from passing through or making basic use of land (Exploration Rights are permanent and universal). Ownership layers on top of this floor, not instead of it.

### 6.1 Tier 1: Exploration Rights

**Purpose:** To ensure the world is always accessible to all players regardless of territory control states.

**Inputs:** None. This is the default state of all land.

**Rules:**

1. Exploration Rights are the permanent, universal baseline for all land in the Dern. No player, guild, or faction can revoke another player's Exploration Rights.
2. Under Exploration Rights, any player may: pass through any zone; observe geological state; use the Read phase; extract from Common Ground nodes; interact with publicly accessible NPCs.
3. Exploration Rights do not grant extraction priority on deep-field resource nodes (that requires Claim Stakes), nor do they grant construction or modification rights (that requires Development Rights).

**Outputs:** Unrestricted zone traversal and Common Ground access for all players.

**Edge Cases:**
- *A guild physically blockades a zone entrance:* Player bodies cannot block zone entrances. Zone transitions are server-enforced, not player-enforced. A guild can contest a zone but cannot deny the transition. This is a hard rule.

---

### 6.2 Tier 2: Claim Stakes

**Purpose:** To enable temporary extraction priority over high-value resource areas, creating competitive resource dynamics without locking out other players permanently.

**Inputs:**
- Player or guild declaring a Claim Stake
- Zone's current Claim Stake density (maximum stake density per zone size is a System Designer tuning parameter)
- Whether the zone is contested (affects automatic Contention triggering)

**Rules:**

1. A Claim Stake is placed at the player's current location in the world. Placement requires: a Claim Stake item (consumable, acquirable from faction trade posts); no existing active Claim Stake within the placement radius (exact radius: System Designer specification required).
2. A placed Claim Stake is visible to all players: a physical flag marker in the world and a marker on the zone map. Claim Stakes cannot be hidden.
3. A Claim Stake lasts 72 real-world hours from placement. To persist beyond 72 hours, the owning player or guild must renew it (costs a Claim Stake item; requires physical presence within the stake radius).
4. **Extraction priority:** Other players can still extract from a staked area, but at reduced yield (the stake holder's claimed portion). Automated extraction systems (bots, unattended scripts) are blocked entirely within the staked area for non-holders. The exact yield reduction percentage for non-holders requires System Designer specification.
5. **Contention Events:** Any player can challenge an active Claim Stake. Challenging triggers a Contention Event. Additionally, any Claim Stake that goes undefended (no stake-holder activity within the stake radius) for 12 consecutive hours in a contested zone automatically enters Contention status.

**Contention Event mechanic (sign-off required — OQ-001):** The specific resolution mechanic for Contention Events has not been designed at this stage. The design intent is that Contention should be accessible to all player archetypes (not exclusively a PvP combat resolution). A tiered challenger-choice system has been proposed (challenging player chooses resolution type; defending player receives home-territory advantage in all modes). This requires System Designer specification before Phase 1.

**Outputs:**
- Extraction priority over non-holders in the staked area
- World-visible ownership marker
- Contention event trigger (if challenged or abandoned)

**Edge Cases:**
- *Claim Stake placed in a zone that subsequently undergoes a major geological event:* The geological event may physically destroy the staked node (if terrain alteration is involved) or make the zone uninhabitable temporarily. If the node is destroyed, the Claim Stake is dissolved. The stake holder receives no compensation — geological volatility risk is disclosed at zone entry (see Section 6.3).
- *A player places a Claim Stake and immediately logs off:* The stake persists. The 12-hour undefended clock begins immediately upon placement. If the player does not return within 12 hours in a contested zone, the stake enters Contention. This is intended — Claim Stakes require active engagement.

---

### 6.3 Tier 3: Development Rights

**Purpose:** To enable permanent player-built territory with world-legible ownership, faction significance, and realistic geological risk disclosure.

**Inputs:**
- Zone accessibility to the purchasing faction
- Zone geological stability score (calculated from proximity to active fault lines, historical tectonic event frequency, current precursor event status)
- Player/guild Civilizational Contribution Score threshold (minimum to be specified by System Designer)
- Resource payment appropriate to structure type

**Rules:**

1. Development Rights are purchased from the player's faction. The faction must have an established presence in the zone (either from core world hand-crafted territory or from faction-triggered procedural generation).
2. **Geological stability disclosure:** The zone's geological stability score is displayed explicitly before purchase confirmation. This score reflects proximity to active fault lines, historical event frequency, and current precursor event status. Players who purchase in high-risk zones are making an informed risk/reward decision.
3. Development Rights are persistent until one of three termination conditions:
   - (a) Forcibly taken through a siege mechanic (full siege mechanic design deferred to Phase 1 design)
   - (b) Rendered uninhabitable by a geological event that was not mitigated
   - (c) Abandoned (see decay rules below)
4. **Construction requirements:**
   - Resources scaled to structure size and complexity
   - Structures must use materials architecturally appropriate to the biome's geological character. Building against geological logic (e.g., Varekian platform-city design on seismically active volcanic plateau without adaptive foundation work) produces structural instability that accumulates over time and eventually results in structural failure
   - All player-built structures are visible to all players and contribute to civilizational density (feeding the demographic procedural generation trigger)
5. **Destroyed structures become ruins.** Ruins have salvage value and eventual Legend Layer significance. Loss is painful but not erasure of Legacy.

**Decay timeline for abandoned structures:**

| Time Since Last Owner Activity | Structure State | Player Impact |
|---|---|---|
| 30 days | Decay begins | Structure shows visible deterioration; no functional change yet |
| 60 days | Abandoned status | Faction ownership claim lapses; any player may occupy |
| 90 days | Advanced deterioration | Reduced functional capacity; partial salvage available |
| 180 days | Ruin state | No longer functional; historically significant; fully salvageable |

**Modification to baseline decay:** Structures with active Ledger entries (historical significance) decay more slowly. The exact multiplier is a System Designer tuning parameter (see OQ-005). The intent: very significant structures (e.g., the site of a major faction battle) can persist as ruins indefinitely, eventually entering the Legend Layer as permanent historical landmarks.

**Geological protection:** Players can invest in Deepwalker-knowledge geological dampening structures that reduce tectonic impact on their territory. These installations are not foolproof against very large events but provide meaningful counterplay. They also create faction interdependence — Varekian and Tide Compact players have economic incentive to engage with Deepwalker knowledge even if they are not Deepwalker-aligned.

**Outputs:**
- Permanent player-built structures in the world
- Faction civilizational density increase in the zone
- Potential Historical Ledger entries for significant constructions

**Edge Cases:**
- *Player builds a structure in a zone that then generates a geological event within the precursor window:* The player received the 7-day warning. The risk was disclosed at purchase. No compensation mechanism exists for geological event losses in high-stability-score zones that were accurately disclosed. Players in very low stability zones with active precursor events were warned.
- *Guild disbands after acquiring Development Rights:* Development Rights revert to the last active officer's personal account. If all accounts in the guild become inactive, the decay timer begins from the date of last officer activity.
- *Player builds a structure that physically blocks another player's path:* Zone transitions are server-enforced (see Tier 1 edge cases). Structures cannot block zone transitions. Within a zone, structures can create navigation obstacles — this is intentional territory-defense gameplay — but cannot produce a complete traversal block. Minimum passage width is a technical parameter.

---

### 6.4 Terrain Destruction

**Purpose:** To make permanent terrain alteration a high-cost strategic act, not a casual side effect of play.

**Inputs:**
- Player's Shaping discipline depth (Formation minimum; Mantle for major alteration)
- Shaping resource expenditure
- Zone's current geological state (some zones are more susceptible to terrain alteration than others)

**Rules:**

1. Terrain destruction requires Formation-level Shaping minimum. Major terrain alteration (changing elevation, collapsing a cave system, redirecting a watercourse) requires Mantle-level.
2. Terrain destruction consumes costly Shaping resources. The economic cost is calibrated to make destruction non-trivial even for high-depth Shaping players.
3. Destroyed terrain takes a new geological path. It does not regenerate to its previous state. Ever.
4. Destruction of terrain in contested zones or terrain containing established player structures generates a faction Historical Ledger entry if it meets the significance threshold.
5. Terrain destruction releases materials (rubble, freed mineral content) at lower yield than proper extraction. Destruction is not a mining shortcut.

---

## 7. Faction System

### Overview

Four major civilizations exist in Dern Varath, each with distinct territorial, cultural, and agenda characteristics. The faction system operates through the Historical Ledger — a shared event record that tracks civilizational memory and drives NPC behavior, player reputation, and world state.

### 7.1 The Four Civilizations

---

**The Varekian Compact**

- **Territory:** The Varek River Delta and surrounding lowland river basins
- **Cultural identity:** Pragmatic, mercantile, engineering-minded. Survivors of the Fracturing by adaptation rather than elevation. They believe in contracts, hydraulics, and knowing where the next trade comes from. No theology worth speaking of.
- **Architecture:** Platform cities built above floodplain level. Wide, low, modular, relocatable. Horizontal planning.
- **Agenda:** Re-establish pre-Fracturing trade routes. This requires geological prediction (at minimum) or geological control. They want Founder technology for commercial intelligence: to know when trade routes will flood, when passes will become impassable, when new land will be stable enough to build on. They will negotiate with any faction.
- **Combat identity:** Control and redirection. Low direct damage; high crowd control, terrain manipulation, debuff.
- **Discipline affiliation:** Reading (primary)
- **Player relationship:** Default starting faction. Broadest political neutrality. Best access to other factions' territories through trade relationships. Recommended for players who favor economy, intelligence, and diplomacy.

---

**The Ashbound**

- **Territory:** The Scorch Plateau (eastern Dern)
- **Cultural identity:** Expansionist, militaristic, theocratic. Their homeland rose during the Fracturing — they call it the Ascension and consider themselves divinely selected. They believe the Fracturing is incomplete and that their duty is to assist the Dern's purification.
- **Architecture:** Cities carved into volcanic rock. Monolithic, fortress-like, permanent. Every Ashbound city is a fortress that has been lived in long enough to forget it was one.
- **Agenda:** Accelerate the ongoing geological transformation. They want Anchor technology to deliberately reshape lowland geography, elevate chosen territory, displace civilizations they deem unworthy. They are the game's most explicit military expansionist force.
- **Combat identity:** Aggressive overwhelming force. High direct damage, terrain destruction capability.
- **Discipline affiliation:** Shaping (primary)
- **Player relationship:** Faction for players who favor aggressive PvP, territorial conquest, and direct military confrontation. The most confrontational faction quests. Not cartoonish villains — they believe their agenda with conviction.

---

**The Deepwalkers**

- **Territory:** No single surface territory. Underground karst networks beneath a significant portion of the settled Dern.
- **Cultural identity:** Ancient, methodical, deliberately opaque. The oldest continuous civilization in the Dern. The Fracturing barely affected them. They have records and cultural continuity no surface civilization can match. An elder Deepwalker considers a 200-year project a medium-term initiative.
- **Architecture:** Underground cities of cathedral-scale karst chambers. Natural formations are never destroyed — shaped incrementally over generations. Surface presence is intentionally minimal.
- **Agenda:** Protect the deep. They have inherited more Founder knowledge than any surface civilization and will share it selectively, obstruct recovery efforts they consider dangerous, and actively resist any faction using Anchor technology in ways that threaten underground geology.
- **Combat identity:** Patience and attrition. Cave-fighting specialists. Powerful underground; weaker on open surfaces.
- **Discipline affiliation:** Resonance (primary)
- **Player relationship:** Faction for players who favor lore depth, scholarly pursuits, underground exploration, and moral complexity. Deepwalker quests are the primary source of Founder lore. Rewards patience and discretion.

---

**The Tide Compact**

- **Territory:** The Shatter Coast and the archipelago of new islands created by the Fracturing
- **Cultural identity:** Young (300 years), diverse, meritocratic. A confederation of Fracturing-displaced survivors who built something new from the pieces. Status is determined by what you have found, built, or mapped. The most forward-looking civilization in the Dern.
- **Architecture:** Adaptive and designed to be relocated. Modular, weather-tested, functionally practical. Built to be disassembled because the Compact learned early that attachment to geography is a liability.
- **Agenda:** Expand. Map. Claim. They need territory and know that unmapped land is their primary competitive advantage. They want Anchor technology for prediction: knowing where new land will emerge before it does.
- **Combat identity:** Speed and adaptability. Flanking, weather exploitation, controlled withdrawal. Cannot hold ground well but excellent at selecting fights they can win.
- **Discipline affiliation:** Charting (primary)
- **Player relationship:** Faction for players who favor exploration, discovery, maritime gameplay, and first-mover territorial advantage. Most direct access to procedurally generated regions. Most likely to recruit cross-faction players.

---

### 7.2 The Historical Ledger

**Purpose:** To give NPC civilizations persistent memory of significant events, making player actions legible at the civilizational scale and driving emergent narrative.

**What the Ledger is NOT:** Individual NPC memory of specific player interactions. The Ledger is faction-level historical state, not NPC-level encounter log.

**Inputs:**
- Player actions that meet the significance threshold (see OQ-002 for threshold specification)
- Developer-scripted world events (a small percentage of Ledger entries are seeded by the world simulation to ensure a baseline of civilizational activity)
- NPC-generated faction events (patrol discoveries, trade post reports, geological survey findings)

**Rules:**

1. Each of the four factions maintains a Historical Ledger — a structured event log of significant events that affected that faction.
2. Ledger entry format: [timestamp] [event type] [location] [factions involved] [players involved] [significance score] [effect summary: population / territory / resource access / political alignment / threat level]
3. When a player interacts with an NPC, the NPC's dialogue, behavior, and disposition are derived from: (a) the faction's current Ledger state, (b) the NPC's role archetype (merchant, soldier, farmer, etc.), and (c) the player's reputation with the faction.
4. Two players talking to the same NPC in the same village receive the same historical context. The NPC speaks for their people, not for an individual relationship. Players who personally participated in the event that filled the Ledger receive a reputation modifier that changes how the NPC addresses them — but the underlying context is shared.
5. **Ledger capacity:** The Ledger maintains the last N significant events for a faction (exact N is a System Designer tuning parameter). When the Ledger is full and a new significant event occurs, the oldest event ages out into the Legend Layer (see Section 7.3).
6. **Significance scoring:** All Ledger entries carry a significance score based on measurable impact on the five impact dimensions: population, territory, resource access, political alignment, and threat level. The threshold for entry and the scoring formula require System Designer specification (OQ-002).
7. Players can read any faction's Ledger. The Ledger is not secret. It is the game's public record of civilizational history.

**Outputs:**
- NPC dialogue and behavior state (updated when the Ledger changes)
- Player reputation modifiers (for players involved in Ledger events)
- World map flags on locations associated with Ledger entries
- Input to procedural generation demographic trigger (Ledger entries tracking population displacement or migration feed the generation trigger)

**Edge Cases:**
- *Player triggers an event that should enter multiple factions' Ledgers simultaneously:* The event is written to all relevant Ledgers with faction-perspective variants. An Ashbound military victory is written to the Ashbound Ledger as a victory entry and to the Varekian Ledger as a territorial loss entry. Both entries reference the same event with different significance scores (the victor's entry has higher positive score; the loser's entry has higher threat score).
- *A faction's Ledger is entirely filled with events from a single player's actions:* This is a design flag. If a single player dominates a faction's entire Ledger, it suggests either extraordinary player engagement (desirable) or potential exploitation (e.g., manufactured low-significance events flooding the Ledger). The significance threshold must be set to prevent low-effort event flooding. See OQ-002.
- *Player generates a Ledger entry and then their account is permanently banned:* The Ledger entry persists. The world records what happened, not who did it in relation to their account status. The player's name remains in the record.

---

### 7.3 The Legend Layer

**Purpose:** To give historical events a form of persistence beyond the active Ledger, creating the experience of deep civilizational time and allowing players to encounter their own past actions as legend.

**Rules:**

1. When an event ages out of the active Historical Ledger (pushed out by newer significant events), it does not disappear. It decays into the Legend Layer.
2. In the Legend Layer, events are represented as: oral tradition (NPC dialogue references; NPCs speak of the event as "something that happened in my grandfather's time"); monument inscriptions (physical in-world objects placed at event locations); scholarly texts (findable documents in libraries and ruins); geological formation naming (significant geological events that altered the landscape may rename the formation — "The Varekian Breach," "The Ashbound Rise").
3. Legend Layer entries persist indefinitely. There is no second decay removing them.
4. Players who caused events that have since aged into Legend can theoretically outlive the living memory of their actions and encounter them as legend. This is True Persistence made tangible.
5. **LLM dialogue integration (deferred):** Individual NPC dialogue flavor is a candidate for LLM generation, constrained by faction Ledger state and NPC archetype. This is NOT a Phase 0 or Phase 1 commitment. It is a Phase 3+ consideration. The Ledger architecture is designed to accept LLM-generated dialogue as input without requiring it. Template-based dialogue referencing Ledger entries is the implementation target for Phase 1–2.

**Outputs:**
- Persistent oral tradition and text records in the world
- Physical monuments at significant locations
- Player names and event summaries encoded in world geography (renamed formations, renamed settlements)

---

## 8. New Player Experience

### Overview

The first 30 minutes in Unlimited Worlds must accomplish three things simultaneously:
1. Make the player feel the world is alive and different from other MMORPGs before they have been told anything
2. Give them something meaningful to do without requiring explanation of interconnected systems
3. Present a choice with genuine faction consequence before minute 30

**Design law:** No tutorial boxes. Systems teach through interaction with the world.

### 8.1 Onboarding Principles

1. **The world is already in motion.** The player does not start at the beginning of anything. They arrive in a world that has ongoing events, pending problems, and political conditions that existed before them.
2. **NPCs speak to current conditions.** The first NPC the player hears speaks about something locally specific and currently true — not "welcome, adventurer." This is NPC civilizational memory made tangible in the first seconds.
3. **Geography teaches.** Every interaction with the environment yields world information expressed through observation or action — not through pop-ups. The player learns that salt crystals are economically valuable by being able to examine and harvest them, not by reading an inventory description.
4. **Faction tension is visible before the player chooses.** The player witnesses an incompatibility between faction interests — something physically present in the environment — before they are asked to choose a side. They choose with context, not blindly.
5. **The first consequential choice has four meaningful options.** Including the option to decline — not choosing is a valid and meaningful first choice.

### 8.2 First 30 Minutes: Varek Delta (Default Starting Zone)

**0:00–3:00 — Arrival**

The player is aboard a trade barge approaching the Varek Delta platform city. The game begins mid-travel. Before the player can act:
- The delta city is visible ahead: layered, industrial, complex, already in operation
- A departing barge passes the arriving barge — loaded, purposeful; the world is already doing business
- Salt crystal formations rise from the shallows; some are taller than the player character

No tutorial box. The NPC ferryman speaks without prompting. He says something locally specific and currently true — the north channel has been blocked by sandbar shift, merchants have been frustrated for three days, work is available at the Factor's post. This sentence communicates: you are arriving in a real place with current problems. Not a theme park entrance.

**3:00–7:00 — Disembarkation and First Task Selection**

At the dock, a Varekian factor has three tasks posted on a physical board:
- Short-haul delivery (teaches movement and basic economy)
- Survey request: a merchant wants information on a new sandbar formation (teaches the Read phase)
- Flood repair assistance (teaches environmental hazards)

Alongside the task board, a public notice board shows the last three Historical Ledger entries for the Delta region. One is relevant to something visible in the environment — the player can see the consequence of a logged event. The world has a history; they have arrived in the middle of it.

No faction lock yet. The player takes one task freely.

**7:00–15:00 — First Task Execution (Delivery example)**

The player carries a package two platforms over. Along the route:
- Navigation occurs through movement (no tooltip)
- A salt crystal node on a platform edge can be examined: the game returns a geological observation expressed as first-person world detail ("The crystal formed at the boundary where fresh river water meets tidal intrusion — this area has been tidal for at least a decade"). World information through action, not pop-up.
- An NPC conversation about a missing fishing boat is audible in passing — a hook the player can investigate now or return to later
- The receiving merchant's thank-you references the north channel blockage — NPC awareness of current world conditions, delivered naturally

**15:00–22:00 — First Faction Tension**

After the first task, the player encounters a Deepwalker geological surveyor on the platform. He has been hired by the Compact for a survey job but has his own interest. He mentions the cave cavity visible beneath the platform district's stone foundations. The Compact plans to drain it for salt extraction. The Deepwalkers oppose this.

The player is not asked to choose sides. They are shown that two factions have real and incompatible interests about something physically present in the environment they can see. First faction tension moment — planted as information, not as a choice.

**22:00–30:00 — First Consequential Choice**

The factor sends a follow-up: a saltcrystal formation to the east is being approached by a Tide Compact scout party. The Compact wants the player to reach it first and place a Claim Stake. In return, they will offer a formal faction affiliation contract. This is the player's first use of the Claim Stake mechanic — introduced through doing, not through a tooltip.

**The four options:**

| Option | Immediate Consequence | Faction Consequence |
|---|---|---|
| Stake for the Varekian Compact | The Tide scouts return empty-handed; Compact affiliation begins | Varekian reputation: positive; Tide Compact awareness: minor negative |
| Approach the Tide Compact scouts | They are surprised and pleased; counter-affiliation offered | Tide Compact reputation: positive; Varekian factor notes the choice |
| Stake for yourself with no faction flag | You acquire the salt; minor Varekian negative rep; you remain unaffiliated | No faction affiliation; both factions note the independent action |
| Decline to engage | Return to the factor without going; inform them of the situation; they remain neutral | No affiliation; neutral with all factions; valid first choice |

**By minute 30, without a single tutorial box, the player has:**
- Experienced a world already in motion before and after their session
- Interacted with NPC dialogue responsive to current world conditions
- Learned the Claim Stake mechanic through performing it (or consciously chosen not to)
- Witnessed faction tension about a physical object in the environment
- Made a choice with visible, faction-legible consequence
- Received a planted hook (the underground cavity) discoverable only by having paid attention to an NPC conversation

### 8.3 Starting Zones for Other Factions

Each starting biome provides a faction-appropriate equivalent of the above structure:
- **Scorch Plateau (Ashbound):** Arrival mid-patrol; immediate environmental hostility; faction tension involves a territorial border dispute with the Varekian Compact visible from the starting location; first consequential choice involves whether to participate in a border provocation
- **Deepwalker Karst (Deepwalkers):** Arrival via underground passage emergence; immediate sensory shift (near-silence, bioluminescence); faction tension involves a surface-faction survey team at the cave mouth; first consequential choice involves how to handle the intruders
- **Shatter Coast (Tide Compact):** Arrival by ship into a contested harbor; immediate salvage opportunity visible in the shallows; faction tension involves a Varekian trade delegation disputing salvage rights; first consequential choice involves whose salvage claim to support

All four starting zones must satisfy the same three onboarding principles. The specific mechanics and faction tensions differ; the structural experience does not.

---

## 9. Open Questions Register

The following design questions are unresolved as of GDD v0.1. Each is flagged by priority, responsible party, and whether it blocks Phase 1 work.

---

**OQ-001 — Contention Event Mechanic**

- **Description:** When a Claim Stake is challenged, what is the specific resolution mechanic?
- **Options identified:** (a) PvP combat — most dramatic, favors military archetypes exclusively; (b) timed gathering race — inclusive across archetypes; (c) diplomatic/bidding resolution — favors economy archetypes; (d) tiered challenger-choice system with defender home-territory advantage — most inclusive but most complex to design
- **Design intent:** Must be accessible to all player archetypes. Military players should not have exclusive advantage in resource contention.
- **Blocks Phase 1?** Yes — the Land Ownership system cannot be fully implemented without this
- **Responsible party:** System Designer — requires full mechanic specification
- **Sign-off level:** System Designer primary; GDD Writer approval of spec before implementation

---

**OQ-002 — Historical Ledger Significance Threshold**

- **Description:** What magnitude of action qualifies a player action as a Ledger entry? What is the scoring formula for the five impact dimensions (population, territory, resource access, political alignment, threat level)?
- **Stakes:** This threshold determines the entire feel of the game's civilizational memory system. Too low: Ledger floods with trivialities and loses meaning. Too high: most player actions are invisible at civilizational scale, undermining the Living World and True Persistence pillars.
- **Blocks Phase 1?** Yes — NPC dialogue system cannot be prototyped without knowing the Ledger entry structure
- **Responsible party:** System Designer — requires quantified formula with tested thresholds
- **Sign-off level:** System Designer primary; GDD Writer review; lead designer approval given impact on core pillars

---

**OQ-003 — Strata Power Gap Calibration (Mantle vs. Core)**

- **Description:** What is the precise combat power differential between Strata tiers, particularly between Mantle Understanding (26–40) and Core Understanding (41–50)?
- **Stakes:** If the gap is too large, Core players become untouchable and the EVE Online veteran-lock problem replicates. If too small, the long-term progression arc feels unrewarding.
- **Design constraint:** The design intent is compressed power differential — legacy advantages in breadth and access, not raw power multiplication.
- **Blocks Phase 1?** No — balance specification can wait until combat prototype exists; but must be resolved before Phase 2
- **Responsible party:** System Designer — requires balance specification with modeled scenarios
- **Sign-off level:** System Designer primary; external playtest validation before Phase 2

---

**OQ-004 — Terrain Stance Feasibility at 500+ Players**

- **Description:** Can the Terrain Stance system's per-zone geological state tracking perform at 500+ concurrent players per zone? The design specifies zone-event-tick management (not per-frame), specifically to address scale concerns.
- **Stakes:** If technically infeasible, the combat system's geological identity is compromised. Alternative designs (simpler terrain modifiers; per-player stance without zone aggregation) would need to be evaluated.
- **Blocks Phase 1?** No — Phase 1 target is 50 players; validate at Phase 2 (100+ players)
- **Responsible party:** Tech Architect — requires server-side feasibility assessment and performance modeling
- **Sign-off level:** Tech Architect sign-off required before Phase 2 combat implementation. GDD Writer cannot finalize combat system spec without this.

---

**OQ-005 — Decay Timer Calibration**

- **Description:** The 30/60/90/180-day abandonment decay timeline is a first estimate. Should decay timers vary by: (a) structure size (a player shack vs. a faction fortification), (b) historical significance (structures with Ledger entries vs. those without), (c) faction significance (a faction capital outpost vs. a personal workshop)?
- **Stakes:** If decay is too slow, ghost-town server sprawl accumulates. If decay is too fast, players who take extended breaks lose structures that felt permanent.
- **Blocks Phase 1?** No — housing not prototyped until Phase 2; but decay model must be finalized before Phase 2
- **Responsible party:** System Designer — requires tiered decay model specification
- **Sign-off level:** System Designer primary; community/player feedback input recommended before finalization

---

**OQ-006 — Transport PvP Flagging Thresholds**

- **Description:** What constitutes "high-value cargo" for automatic PvP flagging during transport? The distinction between low-value (PvP-protected) and high-value (PvP-flagged, map-visible) transport must be defined.
- **Stakes:** If the threshold is too low, all transport becomes a PvP gauntlet and casual economy players are griefed. If too high, transport interdiction (a faction warfare mechanic) becomes too safe and loses strategic weight.
- **Blocks Phase 1?** No — economy prototype in Phase 2; but must be resolved before Phase 2 economy implementation
- **Responsible party:** System Designer
- **Sign-off level:** Local decision — System Designer can resolve with GDD Writer review

---

**Additional open questions from source sessions (lower priority):**

| ID | Question | Responsible | Phase Blocker |
|---|---|---|---|
| OQ-007 | Monetization model (subscription / B2P / F2P with cosmetics) | Lead Producer | Pre-Phase 3 |
| OQ-008 | Server architecture (monolithic shards vs. seamless world) | Tech Architect | Phase 1 — must be resolved before server prototype |
| OQ-009 | Siege mechanic design (how Development Rights are forcibly taken) | System Designer | Phase 2 |
| OQ-010 | NPC individual dialogue system (template-based vs. LLM; LLM deferred to Phase 3+) | Tech Architect + System Designer | Phase 3 |
| OQ-011 | Contention Event archetype balance (ensure all archetypes have viable contention paths) | System Designer | Depends on OQ-001 resolution |

---

## 10. System Dependencies Map

This section documents what depends on what and what must be designed before what. Use this map to sequence Phase 1 design work.

### 10.1 Hard Dependencies (Design Blocker)

The following systems **cannot be implemented without the prior system being specified**:

```
Historical Ledger [OQ-002: significance threshold]
    └── NPC Dialogue System (NPCs cannot reflect world state without Ledger structure)
    └── Core Gameplay Loop Mark Phase (Ledger entries require Ledger format)
    └── Faction System (faction metrics reference Ledger state)
    └── Geological Legacy System (Legacy Ledger entries reference Ledger format)
    └── Procedural Generation Demographic Trigger (reads Ledger population metrics)

Tectonic Simulation Model
    └── Procedural Generation (all three generation triggers reference tectonic state)
    └── Economy Gathering (node regeneration rates reference tectonic activity)
    └── Land Ownership geological stability score (Tier 3 purchase disclosure)
    └── Geological Cycle weekly loop (requires tectonic simulation output)
    └── Terrain Stance zone state (combat system reads zone geological state)

Geological Discipline System (Strata depths)
    └── Combat Terrain Stance activation (gated by Strata)
    └── Gathering extraction methods (gated by Strata)
    └── Crafting Tier 2 and Tier 3 access (gated by Strata)
    └── Read phase information yield (scales with Strata)
    └── World-gated advancement (requires real locations; depends on world design)

Contention Event Mechanic [OQ-001]
    └── Claim Stakes (Tier 2 Land Ownership cannot be fully implemented without this)
    └── Resource competition loop (Gathering system relies on stake contestation)
```

### 10.2 Soft Dependencies (Interaction, Not Block)

The following systems **interact with but do not strictly block each other**:

```
Anchor Installation System
    ↔ Geological Discipline System (Resonance Core depth required for full interface)
    ↔ Catastrophe generation trigger (installation misuse triggers world generation)
    ↔ Faction Agenda (all four factions have positions on installation use)
    [Note: Anchor installation mechanic not yet designed — required for Phase 2]

Procedural Generation System
    ↔ Faction System (demographic triggers seeded with faction character)
    ↔ Economy (new regions create new resource supply)
    ↔ Land Ownership (new land creates new Development Rights opportunities)
    ↔ New Player Experience (procedurally generated zones are entered by players; onboarding principles must hold in generated zones)

Economy Trade System
    ↔ Land Ownership (controlling resource geography creates economic leverage)
    ↔ Faction System (Synthesis requires cross-faction trade)
    ↔ Geological Legacy (first-finder bonuses recorded in Legacy)
```

### 10.3 Phase 1 Required Decisions (Before Prototype Begins)

The following questions must be resolved before Phase 1 prototype work can begin:

1. **OQ-008: Server architecture** — monolithic shards vs. seamless world affects all server-side system design
2. **OQ-002: Historical Ledger significance threshold** — NPC dialogue prototype requires Ledger structure
3. **OQ-001: Contention Event mechanic** — Claim Stake implementation requires contention resolution

### 10.4 Phase 2 Required Decisions (Before Vertical Slice)

The following questions must be resolved before Phase 2 vertical slice:

4. **OQ-004: Terrain Stance at 500+ players** — Tech Architect validation at 100-player scale
5. **OQ-003: Strata power gap calibration** — Combat balance spec before Phase 2 combat implementation
6. **OQ-005: Decay timer calibration** — Housing and territory decay before Phase 2 land system
7. **OQ-006: Transport PvP flagging thresholds** — Economy transport before Phase 2 economy

---

## Appendix A: Source Document References

| Source | Document Path | Version |
|---|---|---|
| World Architect Session 001 | agents/brainstorming/sessions/2026-05-31-world-architect-session-001.md | Session 001 |
| Mechanic Designer Session 001 | agents/brainstorming/sessions/2026-05-31-mechanic-designer-session-001.md | Session 001 |
| World Primer | docs/lore/world-primer.md | v0.1 |
| Core Gameplay Loop | docs/game-design/core-gameplay-loop.md | v0.1 |

---

## Appendix B: Quick Reference — Measurable Targets

| Target | Value | Source | Status |
|---|---|---|---|
| Core loop cycle duration | 5–15 minutes | Mechanic Designer Session 001 | Confirmed |
| Read phase duration | 1–3 minutes | Mechanic Designer Session 001 | Confirmed |
| Act phase duration | 5–10 minutes | Mechanic Designer Session 001 | Confirmed |
| Mark phase duration | 30 seconds–2 minutes | Mechanic Designer Session 001 | Confirmed |
| Session duration target | 45–90 minutes | GDD Writer synthesis | Confirmed |
| Core cycles per session | 4–6 | Mechanic Designer Session 001 | Confirmed |
| Faction event cycle | 3–5 days real-world | Mechanic Designer Session 001 | Confirmed |
| Geological cycle | 7–10 days real-world | Mechanic Designer Session 001 | Confirmed |
| Market cycle | 5–7 days real-world | Mechanic Designer Session 001 | Confirmed |
| Claim Stake duration | 72 hours | Mechanic Designer Session 001 | Confirmed |
| Claim Stake undefended contention trigger | 12 hours (contested zones) | Mechanic Designer Session 001 | Confirmed |
| Tectonic event minimum precursor window | 7 days | Mechanic Designer Session 001 | Confirmed |
| Structure decay onset | 30 days inactivity | Mechanic Designer Session 001 | Pending calibration (OQ-005) |
| Structure abandoned status | 60 days inactivity | Mechanic Designer Session 001 | Pending calibration (OQ-005) |
| Structure ruin state | 180 days inactivity | Mechanic Designer Session 001 | Pending calibration (OQ-005) |
| Minimum resource type geographic sources | 3 per core world | Mechanic Designer Session 001 | Confirmed |
| Phase 1 player count target | 50 concurrent/zone | Blueprint | Confirmed |
| Phase 2 player count target | 100+ concurrent/zone | Blueprint | Confirmed |
| Phase 3 player count target | 500 concurrent/zone | Mechanic Designer Session 001 | Confirmed |
| Strata depth range | 1–50 | Mechanic Designer Session 001 | Confirmed |
| Strata tier names | Surface/Formation/Mantle/Core | Mechanic Designer Session 001 | Confirmed |

---

*GDD v0.1 — Authoritative for Phase 0. This document is the formal output of the Phase 0 brainstorming sessions. Decisions marked "confirmed" are approved for Phase 1 design. Decisions marked with an OQ reference require resolution before the associated Phase work. No system should be prototyped without resolving its Phase 1 required decisions (Section 10.3). Updates to this document require GDD Writer review and version increment.*
