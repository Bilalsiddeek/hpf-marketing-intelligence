# HPF Trends Memory

Patterns tracked across days and weeks. This is how the agent tells **New** from **Recurring / Strengthening / Weakening / Contradictory / Worth monitoring**.

## Lifecycle

```
Candidate ─(2+ days or 2+ independent sources)─▶ Emerging ─▶ Strengthening ─▶ Established
                                                    │              │               │
                                                    └──────────────┴──▶ Weakening ─▶ Retired
                                       (credible counter-evidence at any stage) ─▶ Contested
```

| Status | Rule |
|---|---|
| `Candidate` | Seen once. Lives in the Candidates table, not yet a trend. |
| `Emerging` | 2–3 sightings, across separate days or independent sources. |
| `Strengthening` | New sightings within 14 days, from more sources or with harder evidence. |
| `Established` | 5+ sightings across 3+ weeks, including at least one primary or data source. |
| `Weakening` | No sighting for 21+ days, or counter-evidence has appeared. |
| `Contested` | Credible evidence on both sides. Log both. |
| `Retired` | No sighting for 45+ days, or disproven. Kept for the record, with a reason. |

**Daily classification of findings** (used in reports):
- **New**: no matching trend or candidate.
- **Recurring**: matches an existing trend; adds no new strength.
- **Strengthening**: adds harder evidence, a new independent source, or wider adoption.
- **Weakening**: counter-signal, reversal, or fading adoption.
- **Contradictory**: directly conflicts with a trend or insight.
- **Worth monitoring**: interesting but too thin to act on.

---

## Active trends

| ID | Trend | Category | Status | First seen | Last seen | Sightings | 8-lens | Relevance to HPF |
|---|---|---|---|---|---|---|---|---|
| _none yet_ | | | | | | | | |

## Trend detail

<!--
Copy for each trend promoted from Candidates:

### T-001 · [Trend name]
- **Pattern:** What keeps happening (facts).
- **Mechanism (interpretation):** Why it's happening. Mark inferences.
- **Who it affects:** Brand stage, category, channel.
- **What would strengthen it / weaken it:** The evidence to look for next.
- **HPF relevance:** Content / acquisition / client strategy / positioning.
- **Evidence log:**
  - YYYY-MM-DD · F-ID · + / − / ≈ · one line · [source](url)
-->

---

## Candidates (seen once, not yet trends)

| Candidate pattern | First seen | F-ID | Category | Notes / what would confirm it |
|---|---|---|---|---|
| _none yet_ | | | | |

---

## Retired trends

| ID | Trend | Retired on | Reason |
|---|---|---|---|
| | | | |

---

## Run Log

| Date | Findings kept | Sources consulted | New candidates | Trend changes | Failures / paywalls |
|---|---|---|---|---|---|
| 2026-10-01 | — | — | — | System built; no research run yet | — |
