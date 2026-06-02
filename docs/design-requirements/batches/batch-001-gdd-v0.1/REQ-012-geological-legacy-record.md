# REQ-012 — Geological Legacy Record Screen

**Domain:** Menu/Screen
**GDD Reference:** Section 2.6 (Long-Term Arc: The Geological Legacy System), Section 7.2 (The Historical Ledger — Ledger entries), Section 7.3 (The Legend Layer)
**Phase Relevance:** Phase 2
**Source Session:** Mechanic Designer Session 001 (Question 2: Outer Loops — long-term progression arc, Geological Legacy System), GDD-v0.1 Section 2.6
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

1. The player's personal Geological Legacy record — a full-screen panel showing the totality of their lasting impact on the Dern. This is a record of world changes, not a character sheet.
2. Territorial Imprint list: land the player has claimed, developed, defended, or destroyed. Each entry shows zone, structure or claim type, current status (active/decaying/ruined/changed-hands), and a brief note about what happened.
3. Faction Ledger Entries: significant events the player triggered that entered civilizational memory. Show entries currently in the active Ledger (still living memory) and entries that have aged into the Legend Layer (now oral tradition/monument). The transition from active to legend should be visually distinct — living entries feel current; legend entries feel like they were carved into stone long ago.
4. Geological Marks: resource nodes discovered, terrain altered, Anchor installations touched. Persistent changes to world geography. Each entry shows what was changed and whether it persists in the current world state.
5. Civilizational Contribution Score (CCS) per faction: a faction-specific measure of contribution to each faction's position. Show all four factions — the player is primarily Varekian aligned but has contributed to others. CCS unlocks access to higher-tier faction content.
6. The record should communicate "Legacy is not power — it is access and meaning." The CCS does not make the player more powerful in direct combat. It gives them historical significance and access.
7. A "current living marks" summary — a quick view of what the player has changed in the world that is still active right now (active Claim Stakes, active structures, Ledger entries still in living memory).

---

## Visual Constraints

**Faction aesthetic:** Varekian Compact (player's primary faction). The Legacy record is the most "archival" surface in the game — it should feel like a personal ledger kept by a mercantile family over generations, combined with a geological survey record.

**Color guidance:** Deep river brown (#3d2b1f) outer frame (like an aged leather-bound record book), aged brass (#b5894f) page dividers, salt-flat white (#e8e4d9) active-ledger entries, aged parchment (#c4b89a) for legend-layer entries (more yellowed, aged), tidal grey-green (#7a9e8e) panel backgrounds, mineral amber (#c49a2f) for discovery attribution markers.

**Active vs. Legend layer visual distinction:** Active Ledger entries should look current — fresh parchment, clear ink, brass-pin active marker. Legend Layer entries should look as if they were inscribed into stone — heavier, more formal typography treatment, slightly carved-looking, on a limestone-toned background rather than fresh parchment.

**CCS display:** Show as a geological cross-section visualization — depth of contribution in each faction visualized as depth in a layered stone column. Not a percentage bar. The depth metaphor: the deeper the layer, the more contribution you have made to that faction's history.

**Tone:** A personal geological record. The gravitas of civilizational contribution. Reading this screen should feel like reviewing a life's work in historical terms, not reviewing character stats.

**Anti-patterns:**
- This must NOT look like a character sheet or an achievement list
- No "achievements unlocked" styling or trophy icons
- No percentage progress bars (use geological depth metaphor instead)
- No power stats — no damage output, no combat ratings, nothing that implies combat power
- No generic MMORPG profile page aesthetic

---

## Claude Artifact Prompt

<!-- Human copies everything between the START and END markers and pastes into a NEW claude.ai conversation -->

[START — PASTE THIS ENTIRE BLOCK INTO CLAUDE.AI AS A NEW CONVERSATION]

You are creating an HTML/CSS UI mockup for an MMORPG called Unlimited Worlds.
This is a pre-production visual exploration — functional interaction is not required.
Produce a single HTML file with embedded CSS that can be opened in a browser.

GAME CONTEXT:
Unlimited Worlds is an MMORPG set in Dern Varath, a world of geological fantasy. Character progression in this game is not about accumulating power — it is about accumulating world impact. A player's Geological Legacy is a persistent record of what they have changed in the world: land claimed, events triggered, resources discovered, terrain altered.

THE GEOLOGICAL LEGACY SYSTEM:
The Geological Legacy has four components:
1. TERRITORIAL IMPRINT: land the player has claimed, developed, defended, or destroyed. Persists until another player changes it.
2. FACTION LEDGER ENTRIES: events the player triggered that entered civilizational memory. Active in the Historical Ledger until newer significant events push them out into the Legend Layer, where they persist as oral tradition, monuments, and scholarly texts.
3. GEOLOGICAL MARKS: resource nodes discovered, terrain altered, Anchor Network installations touched. Permanent changes to world geography.
4. CIVILIZATIONAL CONTRIBUTION SCORE (CCS): faction-specific measure of contribution to each faction's position. High scores unlock access to higher-tier faction content — not higher combat power. A player with a 2-year Legacy is not twice as powerful in combat as a new player. Their Legacy is breadth of access, historical context, and world significance.

THE HISTORICAL LEDGER AND LEGEND LAYER:
Each faction maintains a Historical Ledger — a public record of significant recent events. When the Ledger fills, the oldest events age into the Legend Layer: oral tradition among NPCs, physical monument inscriptions, scholarly texts in libraries. Legend Layer entries persist indefinitely. A player can theoretically outlive the living memory of their own actions and encounter them as legend — as oral tradition NPC dialogue or as inscription on a monument they cannot remember making.

DESIGN PRINCIPLE: Legacy is not power. It is access and meaning.

THE VAREKIAN COMPACT visual identity:
Materials: aged timber, polished river stone, brass fittings, salt crystal accents.
Palette: deep river brown (#3d2b1f) outer frame (aged leather-book binding), aged brass (#b5894f) dividers and section headers, salt-flat white (#e8e4d9) active entries, aged parchment (#c4b89a) for Legend Layer entries, tidal grey-green (#7a9e8e) panel backgrounds, mineral amber (#c49a2f) for discovery/attribution markers, verdigris (#5a8a7a) secondary highlights.
Tone: a personal ledger kept by a mercantile family over generations combined with a geological survey record. Archival, detailed, meaningful.

DESIGN SURFACE:
The Geological Legacy Record screen — a full-screen panel showing a player's complete legacy in the Dern. The player is "KAEL DURST," a Varekian Compact Reading practitioner at Formation Understanding, Strata 17, who has been playing for approximately 3 months of in-world time.

FUNCTIONAL REQUIREMENTS:
1. Screen header:
   "GEOLOGICAL LEGACY — KAEL DURST"
   Subtitle: "Varekian Compact — Formation Understanding — Strata 17"
   Record date: "14th Tide-Turn, Year 423 Post-Fracturing"
   A brief auto-summary line: "18 active world marks. 3 Historical Ledger entries (2 active, 1 legend). 1 active territory claim."
2. TERRITORIAL IMPRINT section:
   Show a table of territorial records:
   - "Reed Bed Western Passage — Passage rights surveyed and registered — STATUS: Active Compact Claim — Date: Last-Ebb, 22nd, Year 423 PF — Note: First survey attribution confirmed in Regional Ledger."
   - "Eastern Salt Crystal Formation — Node ESF-7 — First discovery — STATUS: Active (Claim held by Mira Ashven — Kael Durst retains first-finder yield bonus) — Date: 1st New-Flood, Year 423 PF."
   - "Platform District 4, Sub-foundation — Geological survey report submitted to Compact — STATUS: Active (under review) — Date: 7th Tide-Turn, Year 423 PF."
   - "Northern Reed Bed, Survey Zone 2 — Completed geological survey — STATUS: Historical (survey superseded by new data) — Date: Year 422 PF."
3. FACTION LEDGER ENTRIES section (two sub-sections):
   LIVING MEMORY (active in Historical Ledger):
   - "Varekian Compact Ledger, Entry 7, 14th Tide-Turn Year 423 PF — TERRITORIAL — Reed Bed Western Passage rights registered following KAEL DURST survey completion. Tide Compact access rights confirmed for transit (non-extraction). [ACTIVE IN LEDGER — 22 days remaining at current significance score]"
   - "Varekian Compact Ledger, Entry 3, 7th Tide-Turn Year 423 PF — GEOLOGICAL — Deepwalker geological survey confirmation: subsurface saline cavity beneath Platform District 4 — KAEL DURST survey provided corroborating geological data. [ACTIVE IN LEDGER]"
   These entries should look like current parchment documents — fresh, ink-dark.
   IN THE LEGEND LAYER (aged out of active Ledger):
   - "LEGEND LAYER — Varekian Compact — Northern Survey Route 2, Year 422 PF — KAEL DURST first documented the northern approach sandbar pattern. Survey data led to the Reed Bed Passage route discovery. [Now: oral tradition among Factor's post navigators. Monument: survey post at Reed Bed entrance inscribed with survey attribution.]"
   This entry should look aged — limestone-toned background, heavier typographic treatment, as if inscribed into stone. A different visual register from the active entries.
4. GEOLOGICAL MARKS section:
   - "ESF-7 — Eastern Salt Crystal Formation — DISCOVERED — Year 423 PF — Currently active. 40% yield remaining. First-finder bonus active (+8% precision yield for claim holder)."
   - "Northern Channel Sandbar Survey — Documented geological formation — Year 422 PF — Formation still present. Data contributed to current blockage awareness."
   - "Platform District 4 Sub-Foundation — Geological survey record — Year 423 PF — Cavity confirmed, Deepwalker dispute ongoing."
   Show these as entries in a geological survey record — annotated like field notes.
5. CIVILIZATIONAL CONTRIBUTION SCORE section:
   Show CCS for all four factions as a geological cross-section visualization — four vertical "geological columns" side by side, each representing a faction, showing depth of contribution as layers from the surface down. Deeper = more contribution.
   VAREKIAN COMPACT: Deep column. Multiple contribution layers visible — territorial surveys, Ledger entries, economic contributions. Label highest layer: "Formation Depth — Significant regional contributor. Access: Trade Post senior accounts, Factor's Council observer status."
   TIDE COMPACT: Shallow-medium column. "Surface Depth — Interaction through transit rights cooperation. Access: Tide Compact visitor status."
   DEEPWALKERS: Very shallow. "Surface Depth — Single survey interaction. Access: Polite acknowledgment."
   ASHBOUND: Near-zero. "No significant interaction. Access: None."
   Label the columns with faction names and current access tier. Do NOT show combat power ratings.
6. CURRENT LIVING MARKS summary strip at top or side:
   "Active right now: 1 active Claim Stake (by proxy — Mira Ashven, your discovery node). 2 active Ledger entries. 1 Legend Layer inscription. 3 documented geological survey marks."

VISUAL CONSTRAINTS:
Outer frame: deep river brown (#3d2b1f) — aged leather-bound record book aesthetic. Brass hardware (#b5894f) corner plates.
Active Ledger section: fresh parchment (#e8e4d9) entries, clear sepia ink, brass pin markers.
Legend Layer section: aged parchment (#c4b89a) entries with limestone-toned (#d4cdb8) background panel — heavier typography, as if the text has been absorbed into the material over time.
CCS geological columns: each column is a vertical stack of geological layers — different tones for different contribution eras. Varekian column: deep tidal grey-green layers. Tide Compact: storm grey-blue, shallow. Deepwalkers: mineral amber, very shallow. Ashbound: ash grey, near-empty.
Discovery attribution markers: mineral amber (#c49a2f) brass-pin aesthetic.
Tone: archival, meaningful, personal. This screen is the closest thing the game has to a gravestone and a journal combined. Reading it should feel like reviewing a life's contribution to a place that will remember you after you are gone.
Anti-patterns: this must NOT look like an achievement list or a character sheet. No trophy icons. No percentage bars. No combat stats. No "XP until next level" anywhere. Use geological depth metaphors instead of standard progress UI.

OUTPUT REQUIREMENTS:
- Single HTML file with embedded CSS
- No external dependencies (no CDN links, no Google Fonts — use system fonts or embed @font-face)
- Use the specific Legacy data, Ledger entries, player name, and geological marks given above
- Annotate non-obvious layout zones with HTML comments
- Target viewport: desktop 1920×1080

[END — DO NOT PASTE BEYOND THIS LINE]

---

## Artifact Output Location

`docs/design-requirements/batches/batch-001-gdd-v0.1/artifacts/REQ-012-geological-legacy-record.html`
