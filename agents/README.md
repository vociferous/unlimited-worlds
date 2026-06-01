# Agent Management

This folder contains configurations, prompts, and session logs for all AI agents involved in developing Unlimited Worlds.

## Structure

```
agents/
├── brainstorming/    # Ideation agents — world, lore, mechanics
├── design/           # Document drafting agents — GDDs, specs, balance
├── development/      # Code and architecture agents — reviews, generation
└── configs/          # Shared system prompts and agent personas
```

## Active Agents

| ID | Name | Role | Folder |
|----|------|------|--------|
| AGT-001 | World Architect | Generates and refines world lore, geography, and civilizations | brainstorming/ |
| AGT-002 | Mechanic Designer | Explores and critiques gameplay systems and loops | brainstorming/ |
| AGT-003 | GDD Writer | Drafts formal game design documents from brainstorm outputs | design/ |
| AGT-004 | System Designer | Creates balance models and system interaction specs | design/ |
| AGT-005 | Tech Architect | Evaluates and documents technical architecture decisions | development/ |
| AGT-006 | Code Reviewer | Reviews source code for correctness and standards | development/ |

## How to Use

Each agent folder contains:
- `prompt.md` — the agent's system prompt / persona definition
- `sessions/` — logs of past sessions with that agent
- `outputs/` — finalized outputs produced by the agent

When running a brainstorming session:
1. Choose the appropriate agent
2. Load its `prompt.md` as the system context
3. Save session outputs to `sessions/YYYY-MM-DD-topic.md`
4. Promote finalized content to `outputs/` and link it from `docs/`
