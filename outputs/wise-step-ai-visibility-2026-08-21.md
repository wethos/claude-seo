# AI Visibility Report — wise-step.ro

**Target:** Wise Step Recruiting (IT recruitment agency, Timișoara, Romania)
**Date:** 2026-08-21
**Data source:** DataForSEO AI Optimization API — LLM Mentions dataset
**Cost of this run:** $0.99

---

## Scope limitation (read first)

The request was SE Ranking-style Share-of-Voice across five platforms
(ChatGPT, Gemini, Perplexity, AI Overviews, AI Mode). DataForSEO's LLM
Mentions dataset does not carry that surface set. Verified against
`/v3/ai_optimization/llm_mentions/locations_and_languages`:

| Platform in DataForSEO dataset | Available |
|---|---|
| `chat_gpt` | yes — US/English only |
| `google` (AI Overviews + AI Mode) | yes — 94 locations incl. Romania |
| Gemini | **not in dataset** |
| Perplexity | **not in dataset** |
| Claude | **not in dataset** |

Romania (location 2642) / Romanian: `google` platform only, 458,276 sampled
responses. There is no ChatGPT sample for the Romanian locale.

So this report covers 2 of the 5 requested surfaces. Gemini and Perplexity
SoV require SE Ranking or Profound.

---

## Headline result

wise-step.ro has **1 recorded AI mention** across the entire dataset.

| Field | Value |
|---|---|
| Platform | ChatGPT (`gpt-5-5`) |
| Location / language | United States (2840) / `en` |
| Prompt | "which job is best in romania?" |
| Fan-out query | "best jobs in Romania highest paying careers Romania 2026" |
| Date | 2026-06-14 |
| AI search volume | 13/mo |
| Web-search-based | yes |
| Google AI Overviews (RO) | **0 mentions** |
| Google AI Overviews (any locale) | **0 mentions** |

### The important detail

On that single prompt, wise-step.ro ranked **#1 in ChatGPT's retrieved
search results** with *"IT Salaries in Romania in 2026: The Complete Guide"* —
and was **not cited in the answer**. The citations went to:

- www.romania-insider.com
- www.wall-street.ro
- folositor.ro

Retrieval is working. Citation selection is not. That is a content-shape
problem, not a discovery problem — the page gets pulled in and then loses
the citation to news outlets covering the same salary data.

---

## Share of Voice vs. peer set

Peer set queried via `multi_target_metrics`, all locations/platforms:

| Domain | Mentions | AI search volume | SoV (mentions) | SoV (volume) |
|---|---:|---:|---:|---:|
| ejobs.ro | 893 | 386,867 | 45.96% | 44.70% |
| undelucram.ro | 610 | 334,692 | 31.39% | 38.67% |
| hipo.ro | 287 | 115,538 | 14.77% | 13.35% |
| brainsource.io | 127 | 24,589 | 6.54% | 2.84% |
| rinarecruitment.ro | 25 | 3,760 | 1.29% | 0.43% |
| **wise-step.ro** | **1** | **13** | **0.05%** | **0.00%** |

Confidence: high on the ranking, low on wise-step.ro's absolute figure —
n=1 is a floor reading, not a stable rate. Treat 0.05% as "effectively zero"
rather than a precise number.

The two closest structural comparables are brainsource.io and
rinarecruitment.ro — same business model, same market. brainsource.io
outperforms wise-step.ro by 127× on mentions.

---

## Who owns the category

### Romania / Romanian — prompt space "recrutare it" (202 domains)

| Rank | Domain | Mentions | AI search volume |
|---:|---|---:|---:|
| 1 | www.ejobs.ro | 26 | 8,140 |
| 2 | ro.jooble.org | 20 | 5,550 |
| 3 | www.facebook.com | 18 | 6,400 |
| 4 | www.hipo.ro | 17 | 7,670 |
| 5 | www.bestjobs.eu | 17 | 6,050 |
| 6 | ro.linkedin.com | 17 | 3,880 |
| 7 | www.olx.ro | 12 | 4,580 |
| 8 | ro.wikipedia.org | 7 | 3,030 |
| 9 | www.reddit.com | 7 | 1,740 |
| 10 | www.undelucram.ro | 7 | 1,700 |

Job boards and platforms — not agencies. No recruitment agency ranks in the
Romanian-language top 20. That is an open lane.

### United States / English — prompt space "it recruitment romania" (228 domains)

| Rank | Domain | Mentions | AI search volume |
|---:|---|---:|---:|
| 1 | www.youtube.com | 21 | 5,370 |
| 2 | en.wikipedia.org | 20 | 2,141 |
| 3 | www.linkedin.com | 12 | 4,670 |
| 4 | www.reddit.com | 8 | 521 |
| 5 | www.facebook.com | 7 | 810 |
| 6 | eures.europa.eu | 6 | 640 |
| 7 | www.adecco.com | 5 | 2,050 |
| 8 | rinarecruitment.ro | 4 | 1,820 |
| 9 | brainsource.io | 4 | 1,350 |
| 10 | gobester.com | 3 | 1,770 |
| 11 | www.outsourceaccelerator.com | 3 | 1,770 |
| 12 | clutch.co | 3 | 1,230 |

---

## What actually earns citations in this category

Pages driving peer mentions (`top_mentioned_pages`, brainsource.io +
rinarecruitment.ro):

| Mentions | AI volume | Page |
|---:|---:|---|
| 5 | 1,350 | outsourceaccelerator.com/guide/recruitment-agencies-in-romania/ |
| 3 | 400 | brainsource.io/most-in-demand-jobs-romania-2026/ |
| 2 | 1,180 | brainsource.io/which-recruiting-agency-is-best-for-foreigners-in-romania/ |
| 2 | 100 | brainsource.io/top-10-it-recruitment-agencies-in-romania-2025-guide/ |
| 2 | 100 | goodfirms.co/business-services/staffing/romania |
| 1 | 590 | clutch.co/ro/hr/recruiting |

Three content shapes dominate:

1. **Ranked listicles** — "Top 10 IT recruitment agencies in Romania 2025 guide"
2. **Question-shaped pages** — "Which recruiting agency is best for foreigners in Romania"
3. **Third-party directories** — Clutch, GoodFirms, Outsource Accelerator

Note that directories carry the highest per-page AI volume. LLMs cite the
aggregator, then name the agencies inside it. Being listed in someone else's
guide is currently worth more than owning the guide.

---

## Recommendations

Ordered by expected impact per unit of effort.

### 1. Fix citability on the salary guide (highest leverage)

The page already wins retrieval. It loses the citation to news outlets.
Fixes that address citation selection specifically:

- Add a dated, sourced statistics block near the top — figure, unit, period,
  method, sample size.
- State the methodology explicitly ("based on N placements, Jan–Dec 2026").
  News outlets get cited because they attribute; the guide reads as an
  unattributed claim.
- Write extractable single-sentence answers: "The median IT salary in
  Romania in 2026 is X RON gross/month." One fact per sentence.
- Publish original data the news outlets do not have. Placement data from a
  recruiting firm is exactly the kind of primary source an LLM prefers over
  secondary coverage.

### 2. Get into third-party directories

Clutch, GoodFirms, and Outsource Accelerator are the highest-AI-volume pages
in the category and Wise Step is not in them. This is a listings task, not a
content task, and it is the fastest path to a non-zero mention count.

### 3. Surface the existing Romanian content

458,276 sampled Google AI responses exist for Romania/Romanian, and no
recruitment agency ranks in the top 20 of that prompt space.

The Romanian content already exists — `/ro/` carries a full parallel tree
including 14 translated blog posts. It is simply not being retrieved. Since
the corpus is already written, the work is discovery and citability, not
authoring: verify hreflang between `/` and `/ro/`, confirm the Romanian URLs
are indexed, and apply the same citability fixes from item 1 to the Romanian
salary guide. The uncontested Romanian AI Overview surface is reachable with
content Wise Step already owns.

### 4. Publish the category listicle

"Top IT recruitment agencies in Romania 2026" — brainsource.io ranks on
exactly this title. Being the agency that publishes the comparison is an
established route into these answers, and Wise Step's engineer-founder angle
is a credible differentiator inside it.

### 5. Question-shaped pages matching fan-out patterns

The one recorded mention arrived via fan-out query "best jobs in Romania
highest paying careers Romania 2026" — not via a branded or service query.
Target the question forms directly: "which job is best in romania", "most
in-demand tech jobs Romania", "which recruiting agency is best for
foreigners in Romania".

---

## Methodology

| Endpoint | Purpose | Cost |
|---|---|---|
| `llm_mentions/target_metrics_lite/live` | initial domain check | $0.101 |
| `llm_mentions/target_metrics/live` | full aggregation for wise-step.ro | $0.101 |
| `llm_mentions/search_mentions/live` | prompt-level mention detail | $0.101 |
| `llm_mentions/top_mentioned_domains/live` × 3 | category leaders, RO + US | $0.345 |
| `llm_mentions/multi_target_metrics/live` | peer SoV comparison | $0.106 |
| `llm_mentions/top_mentioned_pages/live` | peer citation-earning pages | $0.115 |
| **Total** | | **$0.99** |

Balance after run: $46.52.

**Confidence notes.** Peer ranking: high — mention counts in the hundreds.
wise-step.ro's own rate: low — n=1. Category leader tables: high, drawn from
202–228 domain samples. AI Overview absence in Romania: high, dataset covers
458,276 RO responses and returns zero for this domain.

**Not covered:** Gemini, Perplexity, and Claude share-of-voice — absent from
the DataForSEO dataset. SE Ranking or Profound required for those surfaces.
