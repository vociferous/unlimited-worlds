# AGT-002 Mechanic Designer — Session 001
**Date:** 2026-05-31
**Agent:** AGT-002 Mechanic Designer
**Topic:** Core Gameplay Loop — All Eight Questions
**Status:** Complete
**Input Materials:** World Architect Session 001, World Primer v0.1

---

## PRELIMINARY: CONSTRAINTS FROM THE WORLD PRIMER

Before touching loop design, I need to flag the constraints that the World Architect's decisions impose on mechanics. These are non-negotiable — mechanics that violate them would contradict the world's identity.

**Constraint 1: Geography is a first-class game resource.**
This means geography must be legible, trackable, and scarce within the gameplay systems. Players must be able to see the value of land, feel the cost of losing it, and understand what they gain by controlling it. Mechanics that treat land as background scenery — as in WoW or FFXIV — are incompatible.

**Constraint 2: Civilizational consequences, not individual consequences.**
The faction Historical Ledger means that player actions matter at the scale of factions, not at the scale of "this NPC now likes me." Mechanic design must produce actions that are faction-legible: actions that factions can notice, interpret, and respond to at civilizational scale. This rules out any mechanic that only produces individual-scale outcomes (e.g., a personal reputation meter that has no faction-wide effect).

**Constraint 3: Scale target of 500+ players per zone.**
This is a hard technical constraint that eliminates or constrains certain combat systems. It also means that individual player actions must be meaningful without dominating shared space. The mechanic design must work with hundreds of simultaneous agents, not around them.

**Constraint 4: Four distinct civilizations with incompatible agendas.**
The mechanic design must produce a world where aligning with any of the four factions is a genuinely different experience, not just a skin over the same activities. If Varekians, Ashbound, Deepwalkers, and Tide Compact all do the same mechanics with different text, the world's depth is wasted.

---

## QUESTION 1: THE CORE LOOP (5–15 MINUTE CYCLE)

### What the Question Is Really Asking

A core loop is not "everything the player can do." It is the repeated unit of action that a player performs without thinking about it — the heartbeat of the game. Everything else nests around it. If the core loop is wrong, no amount of outer content fixes it.

For an MMORPG, the core loop must do five things simultaneously:
1. Be immediately legible to a new player
2. Produce a decision point with meaningful options (not just button-press automation)
3. Deliver a reward on a schedule that sustains engagement (variable ratio reinforcement, but not exploitatively slot-machine-like)
4. Generate a resource or progression token that feeds the outer loop
5. Feel different depending on player archetype (combat player, crafter, explorer, etc.)

### Surveying How Other MMORPGs Handle the Core Loop

**WoW (circa Vanilla/Classic):** Kill X enemies / complete quest objective → receive XP/gold/loot → spend on gear progression → go back out and repeat. The loop is tight, legible, and completely solo-viable. The decision point is gear selection and spec. It creates individual progression but zero world-level consequence — killing 10 wolves near Goldshire does not change anything about Goldshire.

**GW2:** Dynamic event system — events chain, players participate for rewards, events reset. Better than WoW for world responsiveness but ultimately cosmetic — the world resets. The loop: find an event → participate → reward → find next event. Decision points are build optimization. Limitation: resets undermine True Persistence.

**EVE Online:** The clearest example of a loop with genuine world-consequence. Gather/mine → sell/produce → fund ships → go back out. Everything feeds a player-run economy. The loop produces faction-scale consequences (who controls which asteroid belt matters for region economics). The downside: the loop is extremely punishing for casual players and the onboarding is famously brutal.

**FFXIV:** Story progression as the core loop. The loop is: do quest → watch cutscene → unlock next zone → do quest. Combat is mechanical but not punishing. Decision points are rotation optimization. The loop delivers exceptional narrative satisfaction but almost no world-agency. Nothing the player does changes Eorzea.

**Black Desert Online:** Action combat, lifeskill systems, almost no scripted questing. The loop is: gather → process → sell/craft → grind mobs for silver → reinvest. The decision point is where to spend time and silver. BDO gets closest to a Deep Economy loop among mainstream MMOs. The failure mode: the loop is extremely grindy and the upgrade RNG (enhancement system) produces toxic burn-out.

### The Unlimited Worlds Core Loop

The Unlimited Worlds core loop must be built around the world's differentiators. If the loop doesn't express Living World, True Persistence, and geography-as-resource, then those features are marketing copy on a standard MMORPG, not mechanical realities.

**My proposed core loop structure: "Read → Act → Mark"**

Every player, regardless of archetype, performs a three-phase cycle:

**Phase 1: Read (1–3 minutes)**
The player observes the world state and decides what it means. This is not trivial — it is an active skill with mechanical support. World Reading includes:
- Surveying terrain for resource signs (a skilled gatherer reads geological formations to predict resource nodes)
- Checking the faction Historical Ledger for recent events (what has changed since I last logged in?)
- Observing NPC behavior patterns (are patrols heavier today? That signals a faction event)
- Reading environmental indicators of tectonic state (cracking sounds, sulfur smell in new areas, water table changes)

This phase is not downtime. It is reconnaissance. Players who skip it and immediately Act will be less effective and miss opportunities. Players who invest in Read skills (geological survey, faction lore, NPC behavior reading) get substantially better information.

**Phase 2: Act (5–10 minutes)**
The player executes a chosen activity within the world state they just read. Activity types:

- **Combat engagement**: fight in a contested zone, defend an installation, raid a resource node
- **Resource extraction**: mine, gather, fish, or harvest with mechanical depth (not just "stand next to node and wait")
- **Crafting/construction**: convert raw resources into goods, build or upgrade a structure in their claimed territory
- **Exploration**: move into unmapped or procedurally generated territory, document findings, locate Founder ruins
- **Faction operation**: execute a mission that registers as an event on the faction Historical Ledger

Every Act produces: (a) a tangible output (resource, information, structure change, territory change) and (b) a world-state mark.

**Phase 3: Mark (30 seconds–2 minutes)**
The world records what the player did. The Mark is not invisible — it is explicit, visible, and persistent. Forms of marking:
- Resource node depletion (others can see it)
- Faction Ledger update (if the Act met threshold significance)
- Territory change (if the Act involved land)
- Cartographic update (if the Act involved exploration)
- Character's geological imprint (explained in Progression section)

The Mark is what makes the game different from all comparators. In WoW, you kill 10 wolves and they respawn in two minutes. In Unlimited Worlds, you drain a resource node and it is genuinely depleted until geological conditions regenerate it — which may take in-game seasons.

### The Core Loop in One Sentence

**The player reads the world's current state, takes an action that changes it, and leaves a traceable mark — then reads again to see how the world has responded.**

### The Moment-to-Moment Experience (Combat Player)

A combat-focused player in the Varek Delta opens their session and notices (Read phase) that the faction Ledger shows the Ashbound military has pushed forward one zone since yesterday. They check the terrain — the contested salt flat between Varekian territory and the Ashbound advance is flagged as a contested control zone. They join a Varekian defense force (Act phase) — fight through a 10-minute skirmish involving 40+ players, successfully holding the salt flat. The world records (Mark phase) that the salt flat remains Varekian, the Ledger updates, and the Ashbound's advance is noted as stalled. Tomorrow, NPC merchants in the nearest Varekian city will reference the held line.

### The Moment-to-Moment Experience (Gatherer/Crafter)

A crafting-focused Deepwalker player opens their session and reads: the karst cave system in zone 4 has registered increased bioluminescent fungal bloom — that's a geological indicator they know signals a rare mineral upwelling nearby. They navigate underground (Read phase), locate the mineral vein using their geological survey skill. They extract the ore (Act phase, 8 minutes of extraction with mini-game decisions about extraction method — blast vs. careful chisel affects quality/quantity tradeoff). The vein is now 60% depleted (Mark phase). The vein is visible to other players as partially extracted. The rare mineral enters their inventory and eventually the economy.

### Risks in This Loop Design

**Risk 1: The Read phase feels like a tutorial that never ends.**
Mitigation: Make the Read phase mechanically rewarded. Players with high "geological attunement" or "faction intelligence" skills see more information than novices. The Read phase must have skill depth — experienced players get better reads, not just more patience.

**Risk 2: The Mark phase feels like logging an entry.**
Mitigation: Marks must have visible consequences. A depleted node should look different. A changed Ledger entry should show up in NPC dialogue. The Mark must close the feedback loop immediately.

**Risk 3: Players who aren't combat-focused get left behind.**
Mitigation: Every archetype's Act phase must be mechanically substantive. Gathering cannot be "walk to node, press interact, wait." It must require decisions, skill, and world knowledge.

---

## QUESTION 2: OUTER LOOPS (SESSION, WEEKLY, LONG-TERM)

### Session Loop (~1 hour)

The session loop is the question: "What did I accomplish tonight?"

In WoW, the answer is usually "I leveled twice" or "I cleared a dungeon." These are individual milestones. The session loop in Unlimited Worlds must answer differently: "What did I change about the world tonight?"

**Session loop structure:**

A one-hour session should contain 4–6 core loop cycles, plus:
- **One faction-relevant action**: something that touches the faction Historical Ledger or moves a faction metric. This does not have to be dramatic — a significant mineral delivery to a Varekian trade post counts. This is the hook that makes the player feel their hour mattered at a world scale.
- **One exploration or intelligence action**: discovering something new, whether a resource vein, a geological anomaly, a terrain change, or a player-reported event. This feeds into the Emergent Narrative pillar.
- **One social or economic transaction**: selling crafted goods, buying from another player, joining or leading a group activity. This is the glue that makes the economy real.

The session should end with the player feeling they have a "portfolio" of changes they made: the world is not identical to how it was when they logged in.

**How this differs from WoW-style session loop:** WoW session loops are about personal progress. You end the night with more XP, better gear, more gold. None of that changed the world. In Unlimited Worlds, you should end the night with evidence of external change — a territory marker that moved, a Ledger update, a depleted node someone else will notice.

### Weekly Loop

The weekly loop is the aggregate of 3–7 session loops. Its function is to create the perception of civilizational time — the sense that the world is moving on a longer arc.

**Weekly loop structure:**

- **Faction event cycle (3–4 days):** Major faction events — territorial disputes, geological anomaly discoveries, resource crises — fire on a 3–5 day real-time cycle. Players who log in during an active faction event experience a world under pressure. Those who miss it return to a world where the outcome has already been recorded in the Ledger.
- **Geological cycle (7–10 days):** Tectonic precursor events (tremors, unusual tide behavior, NPC migration commentary) are observable over 7–10 day windows before a generation event fires. Players who log in regularly during this window piece together the forecast. Casual players who miss it get the outcome.
- **Market cycle (5–7 days):** Resource supply/demand curves should resolve on weekly timescales. A mineral vein depleted on Monday creates a price spike by Wednesday; if a new vein is discovered by Thursday, prices stabilize by weekend. Players managing economic positions need weekly attention.

**The weekly loop creates a newspaper effect:** players who log in after a few days feel the urge to "read the news" — check the Ledger, check territory maps, check market prices. This is a retention mechanic that is non-exploitative because it is driven by genuine world change, not FOMO-manufactured timers.

### Long-Term Progression Arc (Months/Years)

The long-term arc is the meta-game question: what is the player building toward over months of play?

In WoW/FFXIV, the long-term arc is clear: gear treadmill. Max level → best gear → next expansion resets gear → repeat. This is reliable but produces burn-out and the "content drought" problem (when the treadmill stops, retention collapses).

In EVE Online, the long-term arc is more interesting: build influence, build assets, build a political position. There is no reset. This produces extraordinarily high long-term retention among committed players but extremely low conversion of casual players.

Unlimited Worlds needs a long-term arc that:
1. Produces non-resettable progress (True Persistence)
2. Does not create insurmountable gap between veteran and new players
3. Expresses the geological theme (legacies accumulate like sediment)

**My proposed long-term arc: The Geological Legacy System**

A player's character builds a Geological Legacy over time — a persistent record of their impact on the Dern's geology, economy, and faction history. This Legacy is not a power score. It is a historical record with mechanical consequences.

Legacy components:
- **Territorial Imprint**: land the player has claimed, developed, defended, or destroyed. Persists until someone else changes it.
- **Faction Ledger Entries**: events the player triggered that entered civilizational memory. If the Legend Layer decay hasn't claimed them yet, these are still live. If decay has occurred, they persist as legend text.
- **Geological Marks**: resource nodes discovered, terrain altered, Anchor installations activated or destroyed. These changes to the world remain.
- **Civilizational Contribution Score**: a faction-specific measure of the player's contribution to their faction's position. High scores unlock access to higher-tier faction content, not higher-tier personal power.

The key design principle: **Legacy is not power. It is access and meaning.**

A player with a 2-year Legacy is not twice as powerful in combat as a new player. They have access to deeper faction content, more historical context, more meaningful Ledger entries — but a new player can still influence the world and threaten a veteran's territory.

This solves the new player problem that plagues EVE Online (where older players are untouchable). It creates genuine legacy without creating power gaps that lock out new players.

---

## QUESTION 3: COMBAT SYSTEM DIRECTION

### The Three Options

**Real-Time Action (Elden Ring, BDO, TERA):**
Directional attacks, dodge rolls, manual aim. High skill ceiling, spectacularly expressive, excellent for solo combat. Problems at scale:
- 500 players fighting simultaneously creates visual chaos where individual skill becomes irrelevant — you can't dodge-roll through a crowd
- Server-side hit detection at scale is extremely expensive (latency issues multiply)
- Rewards twitch reflexes, which alienates a significant portion of the MMORPG demographic (older players, players with disabilities, casual players)
- BDO has the best action combat in the MMORPG space and it still struggles with large-scale siege fights (performance degrades, gameplay reduces to AoE spam)

**Tab-Target (WoW, FFXIV, GW2 partially):**
Select target, manage cooldowns and positioning. Lower individual skill expression but scales well to large groups. The rotation management in FFXIV's high-end raids is genuinely deep. Problems:
- Feels dated compared to action combat — new players entering from modern games find it unsatisfying
- Solo combat feels mechanical and low-stakes
- Does not express the geological fantasy setting — there is no reason tab-target combat would feel like fighting in the Dern versus fighting anywhere else

**Hybrid (GW2's approach):**
Positional awareness + skill slots + no auto-attack. GW2 is the best execution of this in an MMORPG context. It scales reasonably to large groups (World vs. World battles in GW2 can involve hundreds of players), maintains individual skill expression, and performs better at scale than full action combat. The failure: GW2's combat still doesn't feel mechanically unique to its world — it feels like skillful ARPG combat that happens to have fantasy dressing.

### My Recommendation: Modified Hybrid — "Geological Combat"

The combat system should be a hybrid with a geological mechanic layered on top. Here is the core idea:

**The Terrain Stance System**

Every biome and sub-region has a geological state (stone type, mineral composition, moisture content, seismic activity). Players who have developed their faction skills (Deepwalker stone-reading, Ashbound volcanic attunement, etc.) can "read" this state and adopt a Terrain Stance — a combat modifier that reflects using the environment's geological character.

A player fighting on obsidian floors (Scorch Plateau) with Ashbound Volcanic Stance gains:
- Heat damage riders on abilities
- Access to magma vent eruption triggers (environmental combat mechanic)
- Reduced mobility (the floor is dangerous to move quickly on)

A player fighting in a salt crystal field (Varek Delta) with Varekian Salt Attunement:
- Crystal fragmentation creates area-denial when struck
- High ground advantage on salt formations (elevated positions from giant crystals)
- Risk of salt storm trigger if too many crystals are destroyed in short window

This system:
- Makes combat feel different in every biome — the geological setting is mechanically expressed, not just visually
- Scales to large fights because terrain stances add zone-level combat layers rather than individual-skill micromanagement
- Works with hybrid targeting (no pure twitch reflex requirement)
- Creates faction-specific combat knowledge that rewards investment

**Technical feasibility at 500 players per zone:**
The Terrain Stance system is server-side state-heavy but not per-hit-calculation-heavy. Terrain state is updated on zone events, not per-frame. Individual combat resolution is standard hybrid hit/dodge calculation. This is achievable. Full-action combat at 500 players is not.

**Rejected option: tab-target only.** A game about a living, mutable world whose geology shapes everything needs combat that reacts to the environment. Pure tab-target cannot express this — it reduces every fight to the same rotation regardless of setting.

**Rejected option: pure action combat.** Scale requirements make this technically inadvisable, and the accessibility risk is real — we would lose the portion of the MMORPG audience that prefers strategic depth over reflexes.

### Faction-Specific Combat Flavor

Each faction must have a combat identity that flows from their lore:

**Varekian Compact:** Control and redirection. Merchants and engineers fight by controlling the battlefield — water-based crowd control, salt crystal terrain manipulation, trapping enemies in flooded or crystalline environments. Low direct damage; high debuff/terrain control.

**Ashbound:** Aggressive, overwhelming force. Volcanic power, fire damage, terrain destruction. High damage, low subtlety. Their combat style is the geological equivalent of "break everything and advance." Difficult to play defensively.

**Deepwalkers:** Patience and attrition. Cave-fighting specialists: darkness manipulation, sound-based disorientation, collapse-trap mechanics. Very powerful underground; weaker on open surfaces. Their combat rewards patience and positioning over aggression.

**Tide Compact:** Speed and adaptability. Maritime combat sensibility — flanking, weather exploitation, rapid repositioning. They cannot hold ground well but are excellent at picking fights they can win and leaving those they cannot.

---

## QUESTION 4: PROGRESSION SYSTEM

### Class-Based vs. Skill-Based — The Real Trade-Offs

**Class-based (WoW, FFXIV):**
Players choose a role archetype (tank, healer, DPS variants) and progress within it. Strengths: clear identity, team composition legibility, easier to balance, social cohesion (players know what each other can do). Weaknesses: limits identity expression, creates "reroll to stay relevant" problem, does not express individual player's relationship to the world.

**Skill-based (EVE, Ultima Online, early BDO):**
Players develop skills through use or through allocation of points. Freedom is higher, but the meta rapidly converges to optimal builds — in practice, skill-based systems usually produce the same archetypes as class-based systems but with more menu management. The additional freedom is often illusory. EVE's skill system is actually a time-gate on horizontal access (learning skills to fly different ships) more than a genuine "play your way" freedom.

**Hybrid skill-within-class (ESO, GW2):**
Classes define a broad role identity, but skill choice within the class creates meaningful variation. This is the best practical approach for large player populations — it provides legibility while enabling meaningful individual expression.

### My Recommendation: Geological Discipline System (Hybrid with World-Integration)

**The Frame:** Character progression is organized around Geological Disciplines — areas of understanding in the world's deep mechanics. These are not classes in the traditional sense ("I am a warrior"). They are domains of knowledge ("I understand volcanic processes at depth X").

**Four discipline tracks (aligned to civilizations but not locked to them):**

**1. Resonance (Deepwalker-aligned)**
Understanding and manipulation of geological resonance — the deep "language" of the Dern. Resonance practitioners can read terrain states, interface with Founder installations, and perform precision geological manipulation. High knowledge requirement; high ceiling. Combat role: support/control. Economic role: Founder ruin investigation, rare material identification, installation activation.

**2. Shaping (Ashbound-aligned)**
Forceful geological manipulation — volcanics, seismic events, terrain destruction and elevation. Shapers are the game's primary terrain-altering class. High damage; high consequence. Combat role: offensive devastation. Economic role: mine development, terrain clearing, fortification destruction.

**3. Reading (Varekian-aligned)**
Geological intelligence — the ability to extract information from terrain, predict changes, and exploit commercial opportunities before others. Readers do not change the world; they read it better than anyone else. Combat role: intelligence and tactical support. Economic role: market positioning, resource forecasting, trade route optimization.

**4. Charting (Tide Compact-aligned)**
Geographical mastery — the ability to move through, document, and claim new territory. Charters are the exploration specialists. Combat role: scouting and mobile skirmishing. Economic role: first-mover advantage on new regions, cartographic trade goods, salvage expertise.

**The Key Design Choice: Disciplines are not mutually exclusive.**

Players choose a primary discipline at character creation (which connects to their starting faction) but can cross-train in secondary disciplines over time. A player who starts as a Varekian Reader can develop secondary Resonance, enabling them to read AND interface with Founder tech — but never as well as a pure Resonance practitioner.

This prevents the "reroll to stay relevant" problem: a Reader who develops secondary Resonance is a distinct archetype with real advantages over a pure Reader. Cross-training is meaningful, not just more of the same.

**How progression connects to the geological theme:**

Progression is measured in Geological Depth — a metaphor that maps directly to the world's lore. A Level 1 Resonance practitioner has surface-level geological understanding. A Level 50 Resonance practitioner has deep geological understanding — equivalent to what Founder scholars understood.

The levels are named after geological concepts, not fantasy tropes:
- Strata 1–10: Surface Understanding (equivalent to "novice")
- Strata 11–25: Formation Understanding (intermediate)
- Strata 26–40: Mantle Understanding (advanced)
- Strata 41–50: Core Understanding (expert; very few players ever reach this)

"I'm Mantle-level in Resonance and Formation-level in Reading" is a more interesting identity statement than "I'm level 35."

**Progression inputs:**

Primary progression comes from doing, not from killing:
- Engaging with geological features relevant to your discipline (Resonance practitioners gain depth from interacting with Founder installations, not from killing 1000 rats)
- Completing faction-relevant events (events that enter the Historical Ledger contribute to discipline progression for participants)
- Discovery actions (first player to document a new geological formation gains a discipline depth bonus)
- Social contribution (teaching lower-depth players via a mentorship mechanic awards modest progression)

**Progression is gated by world access, not time:**
You cannot advance from Formation to Mantle in Resonance until you have interacted with a Mantle-depth geological formation in the world — which means actual exploration or faction access is required. This prevents the WoW problem of players "buying" progression through purely mechanical repetition. Progress requires engagement with the world.

### The New Player Problem

The Strata system must not create the EVE problem: new players unable to compete with veterans. Mitigation:
- Combat power differential between Strata is compressed. A Surface-level Shaper is not 10x weaker than a Core-level Shaper. The difference is breadth of access and precision of ability, not raw power.
- New players in new procedurally generated regions are on equal footing with veterans in those regions — no one has Mantle-depth knowledge of a region that was generated last week.
- Geology changes. Veterans in a disrupted zone lose some of their contextual advantage because the terrain has changed. New players and veterans both need to Re-Read.

---

## QUESTION 5: THE ECONOMY LOOP

### The Core Economic Problem in MMORPGs

Every MMORPG has the same economic failure mode: inflation. Monsters drop gold. Gold accumulates. Prices rise. Veterans are wealthy; new players can't afford anything. The economy loses meaning as a game system and becomes a wealth-accumulation treadmill.

Three approaches to fighting inflation:
1. **Gold sinks (WoW):** Force players to spend gold on consumables, repairs, mounts. Works temporarily; does not address fundamental source (gold always enters faster than sinks remove it).
2. **Player-driven scarcity (EVE):** Resources are finite; ships are destroyed. Everything consumed must be replaced. Extremely effective but requires a specific (brutal) player culture.
3. **Geographic economy (Black Desert):** Resources exist in specific locations and processing chains are complex. Works well until the meta-game solves the optimal path.

Unlimited Worlds has an advantage none of these games had: geography is genuinely mutable and resources are genuinely finite. We can build a more durable economy.

### The Gathering Subsystem

**Core principle: extraction is not passive.**

Resources in Unlimited Worlds are not respawning nodes that a player stands next to for 30 seconds. They are geological formations that require geological knowledge to extract efficiently.

Mechanics:
- **Survey** (Reading discipline): Before extracting, a skilled player surveys the formation to predict quality, yield, and structural risk. A poor survey means unknown quality. A good survey means the player knows whether this vein will yield 50 units of standard ore or 12 units of exceptional ore — different decisions.
- **Extraction method choice**: Each resource node supports multiple extraction methods with different risk/reward profiles. Blast extraction (Shaping technique) is fast but damages surrounding terrain and reduces node total yield. Precision extraction (Resonance technique) is slow but maximizes yield and preserves terrain. Standard extraction (no special discipline required) is middle-of-the-road.
- **Node depletion**: Nodes have finite yield. When depleted, they enter a geological recovery cycle that scales with the world's tectonic state (active tectonic zones recover faster due to new material upwelling; stable zones recover more slowly). Depletion is visible to other players.
- **First-finder bonus**: The first player to discover and document a new node receives a small permanent yield bonus on that node. This incentivizes exploration and documentation, and creates a reason for players to share (or jealously guard) discovery information.

### The Crafting Subsystem

**Core principle: crafting is geological transformation.**

Crafting in the Dern is not a generic inventory-to-output conversion. It is a geological process — the craftsperson is applying geological knowledge to transform raw materials into refined goods.

Three tiers of crafting:
- **Raw processing**: Convert extracted materials into workable stock (ore → ingots, mineral formations → powders, etc.). Requires only basic facility infrastructure. Any player can do this.
- **Geological crafting**: Apply geological techniques to produce goods with properties derived from their origin geology. A weapon crafted from Scorch Plateau obsidian has different properties than one made from Shatter Coast mineral deposits. The origin geology matters — this is expressed in item properties, not just flavor text.
- **Synthesis**: Combine multiple geological sources to produce hybrid materials with properties that neither source material has alone. This requires advanced discipline knowledge and is the highest-value crafting tier. A Resonance practitioner synthesizing Deepwalker rare minerals with Ashbound volcanic ore produces materials that no other process yields.

This system creates:
- Supply chains that map to actual geography (you cannot produce certain synthesis items without resources from at least two biome zones)
- Economic interdependence between factions (factions with hostile agendas may still trade raw materials because synthesis demands it)
- Crafting knowledge as a form of territorial advantage (a crafter who knows what their region's geology produces exclusively can be an economic monopolist)

### The Trade Subsystem

**Core principle: trade routes are geography.**

In most MMOs, the market is a global auction house with no geography. You post something in Stormwind and it is accessible from Orgrimmar. This destroys economic geography.

Unlimited Worlds markets are physically located. There are no global auction houses. Markets exist at:
- **Faction capital markets**: high liquidity, large selection, high prices (intermediaries markup)
- **Regional trade posts**: medium liquidity, regional goods, prices reflect local supply/demand
- **Direct trade**: player-to-player anywhere in the world (no fee, no intermediary, but requires finding the counterparty)

Transport is a gameplay layer: moving goods from production zone to consumption market is an economic activity with risk (theft, geological hazards, distance cost) and reward (price differential). A Deepwalker rare mineral extracted from the Karst and transported to a Varekian Delta market is worth substantially more than selling it locally — but the transport player takes on all the risk.

**How geography-as-resource manifests economically:**

Scenario A: A player or guild controls the primary salt flat near the Varek Delta. Salt is a preservation resource required for food processing. The controlling party can:
- Extract and sell at market (standard mining income)
- Control access rights (charge other players extraction fees)
- Restrict supply to drive up salt prices (economic warfare)
- Trade access to the salt flat as a diplomatic chip to other factions

The salt flat is not just a resource node. It is a real estate asset, an economic lever, and a political position simultaneously.

Scenario B: An Anchor installation is activated and stabilizes a previously unstable volcanic region. Suddenly, a zone that was too dangerous for continuous habitation becomes viable. Land values in that zone shift overnight. Players who predicted this and bought land claims ahead of time have made a political-economic investment. Players who showed up late to a stable zone have missed the founding-era advantage.

Geography changes = economic shocks. This is the "Deep Economy" pillar expressed mechanically.

### Economic Risks to Flag

**Risk 1: Geography control produces oligopolistic dominance.**
If one guild controls all the salt flats, they can strangle the food economy. In EVE Online, large alliances do effectively control essential resources, which creates an oppressive economic environment for smaller players.
Mitigation: Resource distribution must be redundant — no single resource type should exist in only one location. Salt exists in three zones. Obsidian exists in four. Any given supply can be cornered, but not permanently — geology changes, new zones generate, and alternatives exist. Controlling the best supply, not the only supply.

**Risk 2: Transport interdiction creates griefing economy.**
If ganking transport players is trivially rewarding, the trade economy breaks (see EVE's Jita-adjacent ganking problem).
Mitigation: High-value transport goods move in player-organized convoys, which becomes a cooperative social mechanic. Solo transport of low-value goods is safe in most zones. Contested territory transport is a conscious risk-reward choice. PvP flagging for transport zones must be clear and consensual.

**Risk 3: Crafting knowledge monopoly.**
If synthesis recipes are secrets held by a handful of veteran players, they gatekeep the highest-value economy.
Mitigation: Synthesis recipes are geological knowledge, not dropped items — they are discovered through world interaction, and the discovery is attributable (it goes in the Ledger) but the knowledge itself can be shared. Veteran crafters can choose to teach, trade, or keep secrets — all of which produce interesting social dynamics without permanently locking out newcomers.

---

## QUESTION 6: PLAYER RELATIONSHIP TO LAND

### The Fundamental Design Question

This is the hardest question in the design. Land ownership in MMOs ranges from "you own nothing" (most MMOs) to "players own everything" (Ultima Online's original housing, Minecraft servers, EVE sovereignty). Both extremes have serious failure modes.

"You own nothing" collapses the Living World and True Persistence pillars — if no player has skin in specific geography, geography-as-resource is just flavor.

"Players own everything" creates squatting (veterans owning all the prime real estate before new players arrive), excessive PvP griefing, and server sprawl problems.

### Framework: Three Tiers of Land Relationship

**Tier 1: Exploration Rights (no ownership, no permanence)**
Any player can be present in any zone and extract resources. No ownership claimed. This is the default state of all land. The world is accessible.

**Tier 2: Claim Stakes (temporary, contested, faction-backed)**
A player or group can drive a Claim Stake into a resource-rich area, asserting a right of first extraction. A stake:
- Is visible to all players (flag in the world, map marker)
- Lasts 72 real-world hours before requiring renewal
- Can be contested by other players: challenging a stake triggers a Contention Event (a timed competition — not necessarily PvP — where the challenging party attempts to displace the stake holder)
- Gives the stake holder extraction priority (bots and automated extraction are blocked from the staked area for non-holders)
- Does not prevent casual extraction by others — it gives priority, not exclusivity

Stakes are designed for temporary control of active resource situations. They are not permanent ownership.

**Tier 3: Development Rights (permanent, faction-legible, world-shaping)**
For larger permanent structures — settlements, fortifications, trade posts, Anchor installation control points — players can purchase Development Rights from their faction, subject to:
- The zone being accessible to the faction
- The zone having sufficient geological stability for the structure type
- The player/guild meeting a minimum faction Civilizational Contribution threshold
- Payment in resources appropriate to the development type

Development Rights are truly persistent: they last until the land is:
(a) Forcibly taken by another faction/player group (siege mechanic)
(b) Rendered uninhabitable by geological event (tectonic trigger)
(c) Abandoned by the owner for an extended period (decay mechanic — structures deteriorate without maintenance)

**Can players destroy land?**

Yes, with significant cost. The Shaping discipline includes terrain destruction capabilities. Destroying land has:
- Immediate effect: the terrain changes (a hill is leveled, a cave entrance is collapsed)
- Permanent effect: the terrain does not regenerate to its previous state; it takes a new geological path
- Faction consequence: terrain destruction in contested zones registers as a faction Historical Ledger event. It will be remembered.
- Resource consequence: terrain destruction releases materials (rubble, released mineral content) but at lower yield than proper extraction

Terrain destruction is a weapon with real costs. It should not be done carelessly, and the game mechanics ensure it is not done carelessly:
- It requires significant Shaping discipline investment
- It consumes costly Shaping resources
- It produces faction diplomatic consequences
- Destroyed terrain does not simply "respawn"

**Can players build on land they own?**

Yes. Development Rights holders can construct buildings, infrastructure, and faction-specific installations within their territory. Construction mechanics:
- Structures require resources proportional to scale
- Structures must be architecturally coherent with the biome's geological character (you cannot build a Varekian platform city in the middle of a Scorch Plateau zone without the right geological foundation work — failure to adapt produces structural instability and collapse over time)
- Player-built structures are permanent features in the world, visible to all players, and contribute to civilizational density (which feeds the demographic trigger for procedural generation)
- Destroyed structures leave ruins (which become salvage sites for other players, and eventually enter the Legend Layer as historical remnants)

**What happens to player structures when the player quits?**

This is the single hardest problem in MMORPG housing and it must be answered honestly:
- Structures begin decay if no maintenance activity is logged for 30 days
- After 60 days of no maintenance, structures become "abandoned" status — their faction ownership claim lapses, anyone can move in
- After 90 days of abandonment, structures visibly deteriorate
- After 180 days, the structure is a ruin (historically interesting, economically salvageable, but no longer functional)
- Very large or historically significant structures (with Ledger entries) decay more slowly — their historical significance extends their lifespan

This prevents ghost-town server sprawl while creating a historically authentic geology of human habitation: ruins of old settlements dot the landscape, reminding active players of those who came before.

---

## QUESTION 7: FIRST 30 MINUTES

### Design Principles for the New Player Experience

Three principles must hold simultaneously:
1. The player must immediately feel the world is alive and different from other MMOs
2. The player must have something meaningful to do without requiring explanation of 15 interconnected systems
3. The player must make a choice with genuine consequence in the first 30 minutes

Most MMO first-hour experiences fail on principle 3 — the choices are cosmetic (do you want to be a human or an elf?). In Unlimited Worlds, the first consequential choice is faction, and it must be made with enough information to feel real, and early enough to shape the experience.

### The Varek Delta Start (Default Starting Zone) — Step by Step

**0:00–3:00: Arrival**

The player is at a platform ferry dock — they have just arrived in the Varek Delta aboard a trade barge. No loading screen; the game begins mid-travel. In those first three minutes of approach, the world is visible before the player is active in it:
- The delta platform city is visible ahead, complex and industrial
- Another barge is leaving, loaded with something (the world already has economic activity before the player's session)
- The water is wrong: salt crystals rise from the shallows, some taller than a person

No tutorial box appears. Instead, an NPC ferryman speaks about something local and specific — not "welcome to the world of Dern Varath." He says something like: "Tide's come in high this week. Silt Road merchants been complaining about the north channel again. If you're looking for work, the Factor's post is up the main platform."

This communicates: you are arriving in a real place with ongoing concerns, not a theme park zone entrance.

**3:00–7:00: First Decision — Faction Affiliation Prompt**

As the player disembarks, they encounter a Varekian Compact representative at the dock. This is the game's softest possible faction introduction: the representative is not recruiting aggressively, they are doing their job. They have a post board showing three current opportunities:
- A short-haul delivery job (teaches movement, basic economy)
- A survey request (teaches the Read phase; a merchant wants information about a new sandbar formation)
- A help request at a flooded structure site (teaches environmental hazards)

There is no faction lock yet. The player takes one of these tasks.

At this moment, the Historical Ledger entry for this day in the Varek Delta is visible in the environment: a public notice board at the dock reads the last three significant local events. One of them is recent enough to be relevant to something visible in the scene (e.g., "Northern Channel partially blocked — detour via reed beds in effect"). The world has ongoing events; the player has arrived in the middle of them, not at the beginning.

**7:00–15:00: First Task**

The delivery task example (it is the simplest): the player carries a package to a merchant two platforms over. Along the way:
- They navigate the platform city (movement tutorial without a tutorial box)
- They pass an NPC conversation about a missing fishing boat (a planted hook that rewards returning to investigate)
- They encounter a resource node — crystallized salt on a platform edge — with a simple prompt: "Examine?" If they examine it, they learn what it is. If they harvest it (they can), they get a small amount of raw salt and a first-person geological description of the formation ("The salt crystal formed at the water table boundary where fresh river water meets tidal intrusion — this zone must have been tidal for at least ten years"). This is not a tutorial pop-up. It is world information expressed through the action of interacting with the world.

The delivery resolves and the player receives: a small payment and a brief, specific thank-you from the merchant that references the ongoing situation in the world ("Good timing — with the north channel blocked, I wasn't sure this would get through today."). The merchant's awareness of the world's current state is the NPC memory system made tangible to the new player.

**15:00–22:00: The First Faction Moment**

The player receives a follow-up request from the Varekian factor: something slightly larger. Simultaneously, they encounter a Deepwalker representative on the platform — a geologist who has been hired by the Varekian Compact for a survey job but has his own angle. He mentions the cave system entrance visible at the edge of the delta's stone foundations: "The salt crystal growth here follows a pattern consistent with underground saline intrusion. There's a cavity below this district. I've reported it to the Compact — they plan to drain it for salt extraction. The Deepwalkers don't agree with that plan."

This is the first faction tension the player experiences. They are not asked to choose yet — but they have been shown that factions have incompatible interests about something they can see in the world.

**22:00–30:00: First Permanent Choice**

The factor returns with a request: a saltcrystal formation to the east is being claimed by a Tide Compact scout party. The Varekian Compact wants the player to reach it first and place a Claim Stake (first time the player uses this mechanic). If they do, the Compact will formally offer them a faction affiliation contract.

This is the first consequential choice:
- **Stake the formation for the Varekian Compact**: begin Compact affiliation, earn their access and eventual faction perks, begin the Compact's questline. The Tide Compact scout party returns to their ship empty-handed; this may be noted in the Ledger if they come back.
- **Let the Tide Compact have it**: Interact with the Tide Compact scouts instead. They are not hostile — they are surprised a stranger helped them. They offer a counter-affiliation option.
- **Stake the formation for yourself with no faction flag**: You get the salt, but earn minor negative reputation with the Compact (they notice the staking before you've signed anything). You remain unaffiliated.
- **Don't go at all**: Return to the factor, report that you encountered the scouts, and tell the factor you are not ready to commit. You remain unaffiliated longer. This is valid — there is no pressure to affiliate immediately.

Each choice produces a different outcome and a different first 60-minute experience. But all four paths leave the player having: interacted with a living world that was ongoing before they arrived, made at least one real decision with a visible consequence, and understood that factions have genuine interests rather than being quest-givers.

**What the player has learned by minute 30, without a single tutorial box:**
- The world has ongoing events before and after your session
- Geography (the saltcrystal formation) has economic value and political meaning
- NPCs speak to current conditions, not scripted prompts
- Factions have real positions, not just different colored logos
- The mechanics of claim staking (through doing, not a tooltip)
- That the game rewards reading the environment (the Deepwalker geologist's hint about the underground cavity is a hook for a later quest only discoverable by paying attention)

---

## QUESTION 8: TOP 3 BURN-OUT AND EXPLOITATION RISKS

### Risk 1: Geographic Control Monopoly (Exploitation Risk)

**The Problem:**
A large, organized guild could theoretically dominate all critical resource geography — stake all valuable formations, control all trade routes, hold all Anchor installations. This is the EVE Null-Sec problem: a small cartel of veteran players makes the game economically inviable for everyone else.

**Why This Risk Is Higher Than In Other MMOs:**
Geography is more important here than in any comparable game. Because land is an actual resource, not just background, the incentive to hoard it is higher.

**Mitigation Suite:**
1. **Redundant resource distribution**: No single resource type has fewer than 3 distinct geographic sources in the core world. Controlling all of them simultaneously requires an enormous coordinated effort and is itself a Ledger-level faction event — visible to the entire server. Domination is not invisible.
2. **Geological churn**: Tectonic events periodically shift resource geography. A guild that controls the premium salt flat may find it partially submerged in a flood event, or that a new vein has emerged elsewhere. The world resists permanent monopoly organically.
3. **Claim Stake decay under pressure**: A Claim Stake that is not regularly defended can be challenged. High-value stakes that go undefended for more than 12 hours in a contested zone automatically enter Contention status. You cannot hold everything without active attention.
4. **Anti-monopoly faction mechanics**: If a single faction/guild controls resources above a threshold percentage of a region, opposing factions receive a "Resistance Event" bonus — the Historical Ledger broadcasts the control situation and grants bonus rewards to any player who successfully contests the controlling party's stakes. The world's NPC factions push back against monopoly the same way they would in history.

### Risk 2: Resource Node Depletion Misery (Burn-Out Risk)

**The Problem:**
Finite, depletable resources are a double-edged mechanic. When done right (EVE mining), they create genuine scarcity and economic meaning. When done wrong (many crafting games), they produce "I can't find what I need and that's not fun" frustration that burns out casual players.

**Specific Failure Mode:**
A casual player logs in twice a week. Both sessions, they find the resource nodes in their home zone have been depleted by more active players. They cannot progress crafting. The game feels like arriving after the party ended.

**Mitigation Suite:**
1. **Session-respawn zones**: Designated "Common Ground" areas in every zone have nodes that fully respawn per server day. These are lower-yield than deep-field nodes but always available. No player should ever be unable to gather because they didn't log in yesterday.
2. **Depth-scaled access**: The highest-yield nodes are not in the common zones — they require discipline depth and world-exploration investment to find. Casual players have access to reliable but modest supplies; dedicated gatherers have access to exceptional supplies that require proportional effort.
3. **Dynamic respawn rate**: Node regeneration is not on a fixed timer. It responds to geological conditions — a tectonic-active zone regenerates faster. Smart players know where geological activity is currently high (because they can Read the world) and find faster respawn nodes. Casual players who don't know this still have the common-ground guarantee.
4. **Market access**: A player who can't gather can always buy. The trade system must ensure that materials flow from high-production zones to lower-access players via functioning market infrastructure. Crafting should be accessible via buying if gathering is temporarily unavailable.

### Risk 3: Tectonic Events as Involuntary Character Setback (Burn-Out Risk)

**The Problem:**
If a major tectonic event (the game's most dramatic mechanic) can destroy a player's constructed territory without warning or counterplay, it will be experienced as punishing randomness. Players who return from a vacation to find their settlement is now underwater because the game generated a new flood event have a legitimate complaint.

**Specific Failure Mode:**
Player spends two months building a settlement in a volcanic zone. The game fires a Catastrophe Trigger tectonic event that buries the settlement. The player logs in to rubble. They quit.

**Mitigation Suite:**
1. **Precursor event systems**: NO major tectonic event fires without a minimum 7-day precursor window of observable in-world signs. The game's world gives players time to respond, not just inform them of disaster after the fact. Players who read the world and pay attention can prepare, evacuate, fortify, or choose to risk staying.
2. **Geological insurance mechanic**: Players can invest in Deepwalker-knowledge geological dampening structures that protect territory against tectonic impact. This is not foolproof (very large events will overwhelm it) but it provides meaningful counterplay. It also creates a reason to engage with the Deepwalker faction even for Varekian- or Tide-aligned players.
3. **Ruin value**: Destroyed structures become ruins, not empty squares. Ruins are historically interesting, potentially salvageable, and can be rebuilt on the same spot with legacy flavor text ("This structure was built on the ruins of [player name]'s settlement, destroyed in the Great Basin Flood"). Losing a structure is painful, but it is not losing all evidence that it existed.
4. **Explicit risk tiers**: When a player purchases Development Rights, the zone's geological stability score is displayed explicitly. Low-stability zones are disclosed as high-risk — players who build in volcanically active territory know they are accepting a risk/reward tradeoff (lower land cost, richer resources, higher geological volatility). No one should be surprised by a tectonic event in a zone they chose for its volcanic resource wealth.
5. **Event schedule transparency**: The long-term tectonic pressure simulation is partially player-visible. Geological scholars (Reading/Resonance discipline players) can publish forecasts. The server does not hide the geological simulation — it rewards players who invest in reading it.

---

## CROSS-CUTTING OBSERVATIONS

### What Makes This Design Coherent

The design above works as a unified system because the geological theme is not decorative — it is the operating principle of every mechanic:

- The core loop (Read → Act → Mark) is the geological process of observation, event, and record
- The combat system (Terrain Stance) makes geology the battlefield condition
- The progression system (Geological Disciplines + Strata depth) is the player becoming more geologically fluent
- The economy (finite extraction, geographic trade, geological crafting) is geography as capital
- Land ownership (stakes and development rights) is human civilization doing what it always does: claiming geography
- The new player experience teaches all of this through immersion in a specific geological situation (the salt crystal formation, the underground cavity, the tidal flood)
- The burn-out risks are addressed through the geological metaphor: the world gives warning before catastrophe, resources are deep and scarce but findable, and monopoly is broken by the world's own dynamism

### Decisions That Need External Input Before GDD Formalization

1. **Technical feasibility of Terrain Stance system at 500+ players:** The combat system described requires per-zone geological state tracking. This needs a conversation with the Tech Architect about server-side state management costs. The system is designed to be feasible, but it must be validated.

2. **Claim Stake Contention mechanic design:** The Contention Event triggered when a stake is challenged has not been fully designed. It needs specific mechanic definition — is it PvP combat? A timed gathering race? A diplomatic negotiation? This is a key pressure point in the economy loop.

3. **Historical Ledger significance threshold:** How significant does an action need to be to enter the faction Historical Ledger? This threshold determines the entire feel of the game's "world memory" system. Too low and the Ledger floods with trivial events. Too high and players feel their actions don't matter. This needs a System Designer pass to quantify.

4. **Strata depth compression at the top:** If Core Understanding (Strata 41–50) represents Founder-level geological mastery, the power difference between Mantle (26–40) and Core must be calibrated very carefully. Too wide a gap creates the EVE problem; too narrow a gap makes the long-term progression arc feel unrewarding.

5. **Decay timer calibration for abandoned structures:** The 30/60/90/180-day decay timeline proposed in Question 6 is a first estimate. It needs iteration and possibly different tiers by structure size and faction significance.

---

## DECISIONS READY FOR CLEAN OUTPUT

**Core Loop:** Read → Act → Mark (three-phase cycle, every archetype variant)
**Session Loop:** 4–6 core cycles + one faction-relevant action + one exploration/intelligence action + one economic transaction
**Weekly Loop:** Faction event cycle (3–5 days) + geological cycle (7–10 days) + market cycle (5–7 days)
**Long-Term Arc:** Geological Legacy System (territorial imprint + Ledger entries + geological marks + civilizational contribution)
**Combat System:** Modified hybrid with Terrain Stance (geological environment as combat modifier; faction-specific combat identities)
**Progression:** Geological Discipline System (Resonance/Shaping/Reading/Charting) + Strata depth (1–50, geological naming convention)
**Economy:** Gathering (active extraction with depletion) + Crafting (geological transformation with origin-based properties) + Trade (physical market locations, transport layer)
**Land Ownership:** Three-tier system (exploration rights / claim stakes / development rights), with decay mechanics and geological volatility disclosure
**New Player Experience:** Arrival in media res in Varek Delta; faction choice in first 30 minutes; world-legible through action, not tutorial boxes
**Burn-Out Mitigation:** Redundant resources + common-ground nodes + precursor event windows + geological insurance + explicit risk disclosure at land purchase

Proceeding to clean output document.
