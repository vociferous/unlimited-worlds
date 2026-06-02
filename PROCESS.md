# Design Requirements Process

How design requirements are produced, reviewed, and turned into visual mockups via claude.ai.

**Two-minute read.** For full detail on any step, see the file references at the bottom.

---

## Overview

After each planning agent session completes, AGT-007 (Design Requirements Analyst) reads
the session outputs and produces a batch of REQ-XXX design requirement files. A human
reviews each requirement, approves or defers it, then generates a visual mockup by pasting
the embedded prompt into claude.ai as a new conversation. The HTML artifact is saved back
to the project.

```
PLAN SESSION COMPLETES
        │
        ▼
STEP 1 — TRIGGER (human)
Tell Claude Code: "Run AGT-007 on <session>, batch name <batch>, last REQ ID <REQ-XXX>."
        │
        ▼
STEP 2 — AGT-007 RUNS
Reads session files → writes REQ-XXX.md files + session log + TRACKER.md rows.
All Status = PENDING.
        │
        ▼
STEP 3 — HUMAN REVIEW  ◄── KEY GATE
For each REQ-XXX.md:
  • Check GDD Reference is valid
  • Check Claude Artifact Prompt is self-contained (no "see world primer" shortcuts)
  • Check Phase tag is appropriate
  • Mark: [x] APPROVED | [x] REVISED (add notes) | [x] DEFERRED
  • Update Status in TRACKER.md
        │
        ▼
STEP 4 — ARTIFACT GENERATION (human + claude.ai)
For each APPROVED REQ:
  1. Open REQ-XXX.md → locate "Claude Artifact Prompt" section
  2. Copy the entire block inside it
  3. Open a NEW conversation at claude.ai (not a continuation)
  4. Paste and send
  5. Review HTML mockup in the artifact canvas; iterate in-chat if needed
  6. Download HTML → save to:
     docs/design-requirements/batches/<batch>/artifacts/REQ-XXX-<slug>.html
  7. Update TRACKER.md: Status → ARTIFACT, set Reviewed date
        │
        ▼
STEP 5 — CLOSE BATCH
When all REQs are ARTIFACT | DEFERRED | REVISED-IN-PROGRESS:
  Update Batch Index in TRACKER.md. Batch is closed.
```

---

## REVISED Requirements

When a REQ is marked REVISED:
1. Add review notes explaining what is wrong (in the REQ file's Review notes field)
2. Tell Claude Code: "Run AGT-007 to revise REQ-XXX per the review notes. No new requirements."
3. AGT-007 rewrites the file in place; session log records the revision
4. Human re-reviews

---

## File Locations

| What | Where |
|------|-------|
| AGT-007 system prompt + sessions index | `agents/requirements/prompt.md` |
| AGT-007 session logs | `agents/requirements/sessions/YYYY-MM-DD-<batch>.md` |
| All agent personas | `agents/configs/agent-personas.md` |
| Requirement files | `docs/design-requirements/batches/<batch>/REQ-XXX.md` |
| Generated artifacts (HTML) | `docs/design-requirements/batches/<batch>/artifacts/REQ-XXX-<slug>.html` |
| Central status tracker | `docs/design-requirements/TRACKER.md` |
| This document | `PROCESS.md` (project root) |

---

## Design Domains

| Domain | What it covers |
|--------|---------------|
| UI/HUD | In-game overlays during play: health, geological indicators, Ledger badge, Claim Stake timer, Strata depth, Terrain Stance indicator |
| Menu/Screen | Out-of-play screens: character creation, faction select, inventory, crafting, market, map, Geological Legacy, settings |
| World/Environment | In-world physical objects and space aesthetics: notice boards, architecture per faction, terrain, lighting, ruins, monuments |
| Brand/Identity | Out-of-game surfaces: logo, login screen, loading screens, icon set, typography system |

---

## Phase Gate

All Phase 1 requirements (REQ tagged "Phase 1") must reach **ARTIFACT** status before
Phase 1 prototype planning locks. Track progress in `docs/design-requirements/TRACKER.md`
under "Phase 1 Design Completeness."
