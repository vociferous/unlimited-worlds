# Design Requirements Tracker

Central registry of all REQ-XXX design requirements across all batches.  
Updated by AGT-007 after each batch run and by the human reviewer after each review session.

## Status Key

| Status | Meaning |
|--------|---------|
| PENDING | Produced by AGT-007; not yet reviewed by human |
| APPROVED | Human-approved; Claude artifact not yet generated |
| ARTIFACT | Artifact generated and saved to batches/`<batch>`/artifacts/ |
| REVISED | Returned to AGT-007 for revision; review notes in REQ file |
| DEFERRED | Deferred to a later phase; reason in REQ file |

---

## Requirements Registry

| ID | Title | Domain | Phase | Batch | GDD Ref | Status | Reviewed |
|----|-------|--------|-------|-------|---------|--------|---------|
| REQ-001 | Game HUD (In-Play Persistent Overlay) | UI/HUD | Phase 1 | batch-001-gdd-v0.1 | §2.1, §2.3, §3.3, §4.2, §6.2, §7.2 | PENDING | — |
| REQ-002 | Terrain Stance Activation Indicator | UI/HUD | Phase 1 | batch-001-gdd-v0.1 | §4.2, §4.3, §4.4 | PENDING | — |
| REQ-003 | Faction Historical Ledger Notice Board | World/Environment | Phase 1 | batch-001-gdd-v0.1 | §7.2, §8.2, §2.1 | PENDING | — |
| REQ-004 | Character Creation / Faction Selection Screen | Menu/Screen | Phase 1 | batch-001-gdd-v0.1 | §7.1, §3.1, §8.1, §8.2 | PENDING | — |
| REQ-005 | New Player Arrival Screen (Varek Delta) | UI/HUD | Phase 1 | batch-001-gdd-v0.1 | §8.2, §8.1, §8.3 | PENDING | — |
| REQ-006 | Game Logo / Wordmark | Brand/Identity | Phase 1 | batch-001-gdd-v0.1 | §1, World Architect §OQ1 | PENDING | — |
| REQ-007 | Login / Loading Screen | Menu/Screen | Phase 1 | batch-001-gdd-v0.1 | §1, §7.1, World Architect §OQ3 | PENDING | — |
| REQ-008 | Crafting Interface | Menu/Screen | Phase 2 | batch-001-gdd-v0.1 | §5.2, §3.1, §5.1 | PENDING | — |
| REQ-009 | Resource Node Depletion Overlay | UI/HUD | Phase 2 | batch-001-gdd-v0.1 | §5.1, §2.3, §6.2 | PENDING | — |
| REQ-010 | Regional Market Screen | Menu/Screen | Phase 2 | batch-001-gdd-v0.1 | §5.3, §5.1, §2.5 | PENDING | — |
| REQ-011 | Zone Map Overlay | UI/HUD | Phase 2 | batch-001-gdd-v0.1 | §2.1, §6.2, §7.2, §2.5 | PENDING | — |
| REQ-012 | Geological Legacy Record Screen | Menu/Screen | Phase 2 | batch-001-gdd-v0.1 | §2.6, §7.2, §7.3 | PENDING | — |
| REQ-013 | Varekian Delta Capital Market (Environment) | World/Environment | Phase 3+ | batch-001-gdd-v0.1 | §5.3, §7.1 | PENDING | — |
| REQ-014 | Deepwalker Karst Underground HUD Variant | UI/HUD | Phase 3+ | batch-001-gdd-v0.1 | §4.2, §7.1, §3.1 | PENDING | — |

---

## Batch Index

| Batch | Source Sessions | Date | REQs | Approved | Deferred | Artifacts | Closed |
|-------|----------------|------|------|----------|----------|-----------|--------|
| batch-001-gdd-v0.1 | World Architect Session 001, Mechanic Designer Session 001, GDD-v0.1 | 2026-06-02 | 14 | 0 | 0 | 0 | No |

---

## Phase 1 Design Completeness

All Phase 1 requirements must reach ARTIFACT status before Phase 1 prototype planning locks.

| REQ | Title | Status |
|-----|-------|--------|
| REQ-001 | Game HUD (In-Play Persistent Overlay) | PENDING |
| REQ-002 | Terrain Stance Activation Indicator | PENDING |
| REQ-003 | Faction Historical Ledger Notice Board | PENDING |
| REQ-004 | Character Creation / Faction Selection Screen | PENDING |
| REQ-005 | New Player Arrival Screen (Varek Delta) | PENDING |
| REQ-006 | Game Logo / Wordmark | PENDING |
| REQ-007 | Login / Loading Screen | PENDING |

---

## Phase 2 Design Completeness

All Phase 2 requirements must reach ARTIFACT status before Phase 2 vertical slice planning locks.

| REQ | Title | Status |
|-----|-------|--------|
| REQ-008 | Crafting Interface | PENDING |
| REQ-009 | Resource Node Depletion Overlay | PENDING |
| REQ-010 | Regional Market Screen | PENDING |
| REQ-011 | Zone Map Overlay | PENDING |
| REQ-012 | Geological Legacy Record Screen | PENDING |

---

## Open Design Questions (flagged during batch-001)

| ID | Question | Source REQ | Relevant GDD Section | Priority |
|----|----------|-----------|---------------------|----------|
| DQ-001 | Varekian Compact currency notation — "Compact Tallies (CT)" introduced as placeholder; requires System Designer confirmation | REQ-010 | §5.3 | Phase 2 blocker |
| DQ-002 | Terrain Stance channel visual language — geological animation specification; requires Tech/Art validation | REQ-002 | §4.2 | Phase 1 — pre-combat prototype |
| DQ-003 | Underground depth indicator units — no GDD specification for how depth is communicated to players | REQ-014 | §7.1, §3.1 | Phase 3+ |
| DQ-004 | Faction-neutral HUD skin for unaffiliated players — gap between REQ-001 (Varekian default) and REQ-004 (unaffiliated start option) | REQ-001, REQ-004 | §8.2 | Phase 1 — pre-first-playtesting |
