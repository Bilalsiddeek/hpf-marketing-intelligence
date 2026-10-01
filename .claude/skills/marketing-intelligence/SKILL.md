---
name: marketing-intelligence
description: Runs HPF Media's daily marketing-intelligence cycle. Researches brand strategy, creative, consumer psychology, distribution, social platforms, e-commerce, agencies/competitors and emerging martech from the last 7 days; filters for strategic signals relevant to $3M–$10M founder-led and ethical consumer brands; analyses each through HPF's 3D System and 8 lenses; compares against memory; writes reports/daily/YYYY-MM-DD.md; and updates memory/insights.md and memory/trends.md. Use when Bilal asks for "today's intel", "the daily report", "run marketing intelligence", or "what's moving in marketing".
---

# HPF Marketing Intelligence: Daily Run

Read `CLAUDE.md` first. It defines the audience, the frameworks, the verified tool capabilities and the quality rules this procedure depends on. All paths below are relative to the `hpf-marketing-intelligence/` folder.

Set `TODAY` = the current date (YYYY-MM-DD) and `WINDOW` = the 7 days ending today.

---

## Phase 0: Preflight

1. If `reports/daily/TODAY.md` already exists, write to `TODAY-b.md` instead. Never overwrite.
2. Read every file in `sources/`.
3. Read `memory/insights.md` and `memory/trends.md` in full.
4. Read the 3 most recent reports in `reports/daily/` (ignore `_TEMPLATE.md`) and note every URL already covered. Don't repeat an item unless something new has happened.
5. Run one `WebSearch` to confirm search works. If it fails, stop and tell Bilal. **Never produce a report from memory or training data.**

---

## Phase 1: Discovery (breadth)

Goal: a raw candidate list of about 30–60 items. Cast wide here; cut later.

Run `WebSearch` across all 8 categories using the query bank below. Rotate the wording and add the current month and year to time-sensitive queries. Also run one query per **Tier 1** entry in each `sources/` file (e.g. `<Brand> launch OR campaign OR announces`), and `WebFetch` the newsroom URLs marked **Check daily** in `sources/platforms.md`.

| # | Category | Starter queries |
|---|---|---|
| 1 | Brand strategy | `rebrand consumer brand <month year>` · `founder-led brand strategy` · `brand repositioning DTC` · `consumer brand acquisition <month year>` |
| 2 | Creative & advertising | `ad campaign launch <month year>` · `ad creative trend <month year>` · `UGC creator ads performance` · `Effie OR Cannes Lions case study consumer brand` |
| 3 | Consumer psychology | `consumer behavior study <month year>` · `consumer sentiment survey <month year>` · `behavioral science marketing research` · `Gen Z shopping behavior research` |
| 4 | Distribution | `DTC brand retail expansion <month year>` · `Target OR Walmart OR Costco brand launch` · `TikTok Shop brand sales` · `Amazon brand strategy` · `brand collaboration <month year>` |
| 5 | Social platforms | `Instagram update <month year>` · `TikTok announces` · `YouTube Shorts update` · `Meta ads update <month year>` · `Threads OR Pinterest OR Snapchat ads` |
| 6 | E-commerce & growth | `Shopify announces` · `ecommerce conversion benchmark <year>` · `DTC customer acquisition cost <year>` · `subscription retention brand` · `DTC earnings quarter` |
| 7 | Agencies & competitors | `brand strategy agency launches` · `growth agency acquisition <month year>` · `agency new offering DTC brands` · named entries in `sources/agencies.md` |
| 8 | Emerging martech | `AI marketing tool launch <month year>` · `generative AI ad creative platform` · `AI search shopping ChatGPT Perplexity` · `agentic commerce` |

For each candidate, log: title · URL · publisher · publish date · category · one-line gist. Drop anything outside `WINDOW` unless it's needed as background.

**Tool choice**
- `WebFetch`: any public article, newsroom or IR page.
- Built-in browser (`mcp__Claude_Browser__navigate` then `get_page_text`): JS-rendered pages such as Meta Ad Library, TikTok Creative Center and Google Trends. Read only. Decline non-essential cookies. Never sign in.
- **Never** use Claude in Chrome unless Bilal explicitly asks for it in the current session.

---

## Phase 2: Triage (cut to signal)

Score each candidate from 0 to 3 on each test:

| Test | Question |
|---|---|
| **Relevance** | Would a $3M–$10M founder-led or ethical consumer brand care, and could it act on this? |
| **Change** | Is this a real change (new behaviour, rule, channel economics, consumer shift), or more of the same? |
| **Mechanism** | Is there a transferable *why it works* beyond this one company? |
| **Evidence** | 3 = primary or data · 2 = quality trade press · 1 = operator opinion · 0 = aggregator only |
| **HPF leverage** | Does it feed content, acquisition, client strategy or HPF positioning? |

Keep items scoring **≥ 9/15** with Evidence ≥ 1. Target **6–12 findings** in total. The top 3 by score become Executive Brief candidates.

Discard noise: listicles, "X tips" posts, minor feature tweaks with no strategic consequence, and celebrity campaigns with no transferable mechanism.

---

## Phase 3: Verify (depth)

For every kept finding:
1. `WebFetch` the **primary source** (the company announcement, platform newsroom, filing or study). If a trade article reports it, find and fetch what it cites.
2. Take exact figures and dates **from the source text**. Never round, extrapolate or add numbers.
3. Assign a confidence label:
   - **Verified**: confirmed by a primary source, or by 2+ independent quality sources
   - **Single-source**: one credible source only
   - **Unverified**: couldn't confirm. Allowed only in *Signals To Watch*, never in the Executive Brief.
4. If a fetch fails, is paywalled or is JS-only, record that (e.g. "Primary source not accessible: paywall"). Never imply you read it.

---

## Phase 4: Analyse each finding

Work through this full scaffold for each finding. The report shows a condensed version, but the full reasoning should shape it.

- **What happened**: facts only, cited.
- **What changed**: compared with before, or with the norm.
- **Why it matters**: interpretation, labelled as such.
- **Strategic mechanism**: the cause-and-effect that transfers to other brands.
- **Consumer psychology**: name the principle precisely, e.g. social proof, identity signalling, loss aversion, mere exposure, costly signalling, scarcity, cognitive fluency, mental availability, peak-end, endowment. If none applies, write "None material".
- **Distribution mechanism**: how attention or product reaches people (algorithmic feed, creator network, retail shelf, search, AI answers, word of mouth, earned media, community, marketplace).
- **Business implication** for a $3M–$10M brand.
- **3D placement**: is this mainly a Diagnose, Design or Deploy lesson?
- **8-lens tags**: the 1–3 most relevant of Positioning · Customer · Differentiation · Creative · Demand · Distribution · Conversion · Retention.
- **What HPF can learn**, and **what HPF could test or implement**.
- **Memory status**: New · Recurring · Strengthening · Weakening · Contradictory · Worth monitoring. Cite the related `T-`/`I-` ID.
- **Content extraction** (important findings only):
  - Personal-brand content angle
  - HPF Media content angle, with its pillar (3D System / Marketing Education / Radical Transparency) and best-fit framework from `hpf-scripting-frameworks` (01–07) if one is obvious
  - Potential case study
  - Potential framework
  - Potential client conversation, as a diagnostic question Bilal could open with

**Guardrails:** never invent motives; write "Likely rationale (inference):" instead. Never invent numbers. If the mechanism is a hypothesis, say so.

---

## Phase 5: Write the report

The report structure lives in **`reports/daily/_TEMPLATE.md`**, the single source of truth for the format.

1. Copy `reports/daily/_TEMPLATE.md` to `reports/daily/TODAY.md`. Keep every heading **verbatim**, in the same order.
2. Under its section, add one finding block per kept finding. Answer all 8 questions and keep the *(Fact)* / *(Analysis)* labels.
3. If a section has no kept findings, write "No material signal today." Never pad.
4. Put social-platform findings in the section that matches their mechanism, tagged **Platform**.
5. Fill *What This Means For HPF* with exactly 5 personal-brand ideas, 3 HPF Media ideas, 3 client-strategy opportunities and 3 experiments, each traced to an F-ID.
6. List every cited source under *Sources*, plus any URLs that couldn't be accessed.
7. Remove the template's placeholder and instruction text before saving.

**Style:** direct, plain English, short sentences, no filler and no hype words ("game-changer", "revolutionary"). Every factual sentence must trace to a listed source.

---

## Phase 6: Update memory

### `memory/trends.md`
- **Finding linked to an existing trend:** add an evidence-log line (`TODAY · F-ID · + / − / ≈ · one line`), update *Last seen*, *Sightings* and *Status*.
- **Pattern seen for the first time:** don't create a trend yet. Add it to **Candidates** with the F-ID.
- **Candidate seen on 2+ separate days, or across 2+ independent companies or sources:** promote it to a trend (`T-NNN`, status `Emerging`).
- **Status rules:**
  - `Emerging`: 2–3 sightings.
  - `Strengthening`: new sightings within 14 days, from more sources or with harder evidence.
  - `Established`: 5+ sightings across 3+ weeks, including at least one primary or data source.
  - `Weakening`: no sighting for 21+ days, or counter-evidence has appeared.
  - `Contested`: credible contradictory evidence exists. Log both sides.
  - `Retired`: no sighting for 45+ days, or clearly disproven. Keep the entry and add the reason.

### `memory/insights.md`
Promote an insight (`I-NNN`) only when **both** of these hold:
- it's backed by a trend that's `Strengthening` or `Established`, **or** by strong primary data; **and**
- it changes what HPF says, sells, recommends or makes.

When new evidence supports or contradicts an existing insight, update that insight's evidence and confidence instead of adding a duplicate.

### Run log
Append one row to the **Run Log** at the bottom of `memory/trends.md`: date · findings kept · sources consulted · new candidates · trend changes · failures.

---

## Phase 7: Report back to Bilal

Reply in chat with only:
1. The 3 Executive Brief headlines
2. A link to the report file
3. Memory changes (new candidates, new or promoted trends, status changes, new insights)
4. Any capability problems (failed fetches, paywalls)

Don't paste the full report into chat.

---

## Failure modes to avoid
- **A generic news roundup.** If a finding has no mechanism and no HPF implication, cut it.
- **Big-brand bias.** Translate the lesson down to $3M–$10M, or drop it.
- **Citing aggregators.** Treat "every Meta update" listicles as leads only; find Meta's own announcement.
- **Repeating yesterday.** Check the last 3 reports.
- **Padding empty sections.** "No material signal today." is a valid and useful answer.
