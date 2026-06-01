# Brainstorming Agent Prompts

Load `../configs/agent-personas.md` base context first, then append the relevant persona section below.

## Sessions Index

| Date | Agent | Topic | File |
|------|-------|-------|------|
| 2026-05-31 | AGT-001 World Architect | Setting, differentiation, procedural generation, NPC memory, World Primer | `sessions/2026-05-31-world-architect-session-001.md` |
| 2026-05-31 | AGT-002 Mechanic Designer | Core gameplay loop, combat, progression, economy, land ownership, new player experience | `sessions/2026-05-31-mechanic-designer-session-001.md` |

## Starting a Session

1. Pick AGT-001 (World Architect) or AGT-002 (Mechanic Designer)
2. Load the base context + persona from `agent-personas.md`
3. Present one open question from `BLUEPRINT.md` at a time
4. Save the raw session to `sessions/YYYY-MM-DD-topic.md`
5. Distill key decisions into `outputs/` when the session concludes
