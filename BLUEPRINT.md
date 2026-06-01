# Unlimited Worlds — Project Blueprint

**Genre:** Massively Multiplayer Online Role-Playing Game (MMORPG)  
**Status:** Pre-Production / Brainstorming  
**Started:** 2026-05-31

---

## Vision

Unlimited Worlds is an MMORPG built on the premise that the game world itself evolves — procedurally generated continents, player-driven economies, faction wars that reshape geography, and AI-powered NPCs with persistent memory. No two players experience the same world.

---

## Project Structure

```
unlimited-worlds/
├── BLUEPRINT.md              ← you are here
├── src/                      # All source code
│   ├── client/               # Game client (rendering, UI, input)
│   ├── server/               # Game server (world sim, netcode, persistence)
│   ├── shared/               # Shared logic (entity definitions, protocols)
│   └── tools/                # Dev tools (map editor, asset pipeline, debug)
├── agents/                   # AI agent configurations and logs
│   ├── brainstorming/        # World-building, mechanic ideation agents
│   ├── design/               # Game design document drafting agents
│   ├── development/          # Code generation and review agents
│   └── configs/              # Shared agent configuration files
├── progress/                 # Project tracking
│   ├── milestones/           # Major phase definitions and completion status
│   ├── sprints/              # Sprint-level task breakdowns
│   └── decisions/            # Architecture decision records (ADRs)
└── docs/                     # All documentation
    ├── game-design/          # GDDs, mechanic specs, systems design
    ├── technical/            # Tech stack, architecture, API specs
    ├── art/                  # Art direction, style guides, asset specs
    └── lore/                 # World lore, history, factions, races
```

---

## Core Pillars

| Pillar | Description |
|--------|-------------|
| **Living World** | The world changes based on player actions, seasons, and AI-driven events |
| **True Persistence** | Player legacies, guild histories, and world events are permanently recorded |
| **Emergent Narrative** | Stories emerge from player interactions rather than scripted quests alone |
| **Boundless Scale** | Procedural generation ensures the world is effectively infinite |
| **Deep Economy** | Player-driven crafting, trade, and resource control with real supply/demand |

---

## Phases

### Phase 0 — Brainstorming & World-Building (Current)
- Define core gameplay loop
- Establish world lore and setting
- Draft game design documents
- Explore technical architecture options
- Identify art direction

### Phase 1 — Prototype
- Minimal viable server with basic movement and world state sync
- Placeholder assets and basic terrain rendering
- Core combat loop proof-of-concept
- Basic character creation

### Phase 2 — Vertical Slice
- One fully realized zone with complete gameplay loop
- Working economy (gathering → crafting → selling)
- Basic faction system with two opposing factions
- Multiplayer with 100+ concurrent players per zone

### Phase 3 — Alpha
- Multiple biomes and zones
- Full class system
- Guild and social systems
- PvP zones and faction warfare

### Phase 4 — Beta
- Full world with procedurally extended regions
- Stress test for 10,000+ concurrent players
- Economy tuning and balance pass
- Platform QA

### Phase 5 — Launch
- Soft launch → regional rollout
- Live ops team structure established
- Post-launch roadmap defined

---

## Agent Strategy

Different AI agents handle different domains of the project. See `agents/` for configs.

| Agent Role | Folder | Responsibility |
|------------|--------|----------------|
| **World Architect** | brainstorming/ | Generate lore, geography, civilizations |
| **Mechanic Designer** | brainstorming/ | Explore and evaluate gameplay systems |
| **GDD Writer** | design/ | Draft and refine game design documents |
| **System Designer** | design/ | Balance spreadsheets and system specs |
| **Tech Architect** | development/ | Define and validate technical architecture |
| **Code Reviewer** | development/ | Review PRs and enforce code standards |

---

## Open Questions (Brainstorming Backlog)

- [ ] What is the central setting? (high fantasy / sci-fantasy / historical / original)
- [ ] Turn-based or real-time combat?
- [ ] Class-based or skill-based character progression?
- [ ] Housing system — instanced or world-placed?
- [ ] Monetization model — subscription / B2P / F2P with cosmetics?
- [ ] What makes this MMORPG different from existing titles?
- [ ] Server architecture — monolithic shards or seamless world?
- [ ] What is the player win condition, if any?
- [ ] How are new world regions generated and when?
- [ ] NPC AI depth — scripted, behavior tree, or LLM-powered?

---

## Tech Stack Candidates

| Layer | Options |
|-------|---------|
| Game Engine | Godot 4 / Unreal Engine 5 / Custom |
| Server Language | Go / Rust / C++ |
| Database | PostgreSQL + Redis / ScyllaDB |
| World Generation | Custom procedural / Wave Function Collapse |
| Networking | Custom UDP / WebTransport / ENet |
| Auth & Accounts | Custom + OAuth2 |
| Infra | Kubernetes on bare metal / cloud hybrid |

---

## Immediate Next Steps

1. Run brainstorming agents to answer the open questions above
2. Choose the game setting and write the world primer (docs/lore/)
3. Define the core gameplay loop in detail (docs/game-design/)
4. Evaluate tech stack options and make initial ADRs (progress/decisions/)
5. Sketch the art direction (docs/art/)
