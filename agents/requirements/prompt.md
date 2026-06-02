# AGT-007: Design Requirements Analyst

Load the base context from `../configs/agent-personas.md` first, then load the AGT-007 persona section.

## Sessions Index

| Date | Batch | Source Sessions | REQs Produced | File |
|------|-------|-----------------|---------------|------|
| 2026-06-02 | batch-001-gdd-v0.1 | World Architect S001, Mechanic Designer S001, GDD-v0.1 | 14 (REQ-001–REQ-014) | `sessions/2026-06-02-batch-001-gdd-v0.1.md` |

## How to Trigger a Session

Give AGT-007 the following structured task message:

```
Read the following session(s):
- <path>: <brief description of what the session covers>

Batch name: batch-NNN-<slug>
Last REQ ID used: REQ-XXX (or "none" if this is the first batch)
Phase focus: Phase 1 surfaces take priority

For each design surface you identify, produce a REQ-XXX.md file.
Surfaces to explicitly exclude from this batch: [list any if applicable, or "none"]
```

## REQ File Format

Each REQ-XXX.md file produced by AGT-007 follows this structure:

```markdown
# REQ-XXX — [Short Title]

**Domain:** UI/HUD | Menu/Screen | World/Environment | Brand/Identity
**GDD Reference:** [Section number and title from GDD-v0.1.md]
**Phase Relevance:** Phase 1 | Phase 2 | Phase 3+
**Source Session:** [e.g., AGT-003 GDD Writer Session 001 (2026-05-31)]
**Batch:** [e.g., batch-001-gdd-v0.1]
**Created:** YYYY-MM-DD

---

## Human Review Status

- [ ] APPROVED — ready for Claude artifact generation
- [ ] REVISED — see notes below
- [ ] DEFERRED — reason below

**Review notes:**
<!-- Human fills this in during review -->

---

## Functional Requirements

1.
2.
3.

---

## Visual Constraints

**Faction aesthetic:** [Applicable faction(s) and their visual identity]
**Color guidance:** [Specific palette notes]
**Tone:** [e.g., "industrial-pragmatic; nothing decorative that isn't load-bearing"]
**Anti-patterns:** [What this design must NOT look like]

---

## Claude Artifact Prompt

<!-- Human copies everything inside this section and pastes into a NEW claude.ai conversation -->

[SELF-CONTAINED PROMPT — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
[Full world and faction context embedded here — no external references]

DESIGN SURFACE:
[Description of the specific surface]

FUNCTIONAL REQUIREMENTS:
[Numbered list]

VISUAL CONSTRAINTS:
[All aesthetic guidance embedded here]

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN, no Google Fonts — use system fonts)
- Representative placeholder data (not "Lorem ipsum")
- Annotate non-obvious layout zones with HTML comments

[END OF PROMPT]

---

## Artifact Output Location

When approved and generated, save the HTML file to:
`docs/design-requirements/batches/<batch>/artifacts/REQ-XXX-<slug>.html`
```

## Faction Aesthetic Reference

AGT-007 must embed the relevant section(s) of this reference verbatim inside every Claude Artifact Prompt. Do not use shorthand — claude.ai has no access to this file.

### Varekian Compact
- **Materials:** Aged timber, polished river stone, brass fittings, salt crystal accents
- **Palette:** Tidal grey-green, aged brass, salt-flat white, deep river brown
- **Architecture:** Horizontal, modular, low, wide, built to be relocated
- **UI tone:** Pragmatic, mercantile-ledger, information-dense; nothing decorative that isn't load-bearing

### The Ashbound
- **Materials:** Volcanic basalt, obsidian, forge iron, compacted ash
- **Palette:** Deep volcanic black, forge orange, ash grey, blood-oxide red
- **Architecture:** Monolithic, carved-in, fortress-permanent, vertically imposing
- **UI tone:** Theocratic severity; minimal ornamentation except militaristic heraldry; heavy weight

### The Deepwalkers
- **Materials:** Shaped karst limestone, bioluminescent mineral veins, ancient polished bone
- **Palette:** Deep cave black, bioluminescent blue-green, mineral amber, pale limestone white
- **Architecture:** Organic, shaped over generations following the logic of the material, cathedral-scale
- **UI tone:** Ancient, patient, scholarly; information presented as if carved into stone; slow reveal

### The Tide Compact
- **Materials:** Weathered hardwood, rope and canvas, salvaged metal, waterproofed leather
- **Palette:** Storm grey-blue, salvage rust-orange, sea-glass green, weathered off-white
- **Architecture:** Modular, designed to be disassembled, weather-battered but functional
- **UI tone:** Meritocratic and forward-looking; clean, practical, slightly rough at the edges

### Universal / Multi-faction surfaces
- **Geological base:** Deep stone textures, slate, obsidian, earth tones throughout
- **Magic system:** Geological energy is visual spectacle — crystal growth, heat glow, bioluminescence, slow light through rock
- **Avoid:** Generic fantasy chrome/gold, purple magic auras, floating glyphs without geological grounding
