# Ranked Keywords — wise-step.ro

**Target:** wise-step.ro (Wise Step Recruiting, IT recruitment, Timișoara)
**Location:** Romania (2642), desktop, depth 100
**Date:** 2026-08-21
**Method:** DataForSEO Labs (database) + live Google SERP verification
**Cost of this run:** $0.50

---

## Why this needed two methods

DataForSEO Labs — the endpoint that normally answers "what does this domain
rank for" — returns **nothing** for wise-step.ro:

| Query | Result |
|---|---|
| `ranked_keywords/live` — RO/ro | 0 items, `total_count: null` |
| `domain_rank_overview/live` — RO/ro | 0 items |
| `domain_rank_overview/live` — US/en | 0 items |
| same call for brainsource.io — RO/ro | **18 keywords**, ETV 38.4 |

The endpoint works and the Romanian database is populated. wise-step.ro is
simply not in it — typical for a domain too new or too low-traffic to have
been picked up in DataForSEO's crawl cycle.

**Labs saying "no keywords" is not the same as ranking for nothing.** Live
SERP checks found 9 ranking URLs, including a #1. Anyone reading only the
Labs number would conclude the site has zero organic presence, which is false.

---

## Verified rankings (live SERP)

| # | Keyword | Lang | Rank | Abs | URL |
|---|---|---|---:|---:|---|
| 1 | it recruitment agency timisoara | en | **1** | 2 | `/` |
| 2 | it recruitment trends eastern europe 2026 | en | **2** | 3 | `/blog/it-recruitment-trends-eastern-europe-2026/` |
| 3 | agentie recrutare it timisoara | ro | **3** | 4 | `/` |
| 4 | hire remote developers romania | en | **5** | 6 | `/blog/hire-remote-developers-romania/` |
| 5 | salarii it romania inflatie | ro | **10** | 13 | `/ro/blog/it-salaries-romania-inflation-2026-ro/` |
| 6 | ai data science recruitment romania | en | 11 | 13 | `/blog/ai-data-science-recruitment-romania/` |
| 7 | ai recruitment agency romania | en | 17 | 20 | `/blog/` |
| 8 | it salaries romania 2026 | en | 19 | 22 | `/blog/it-salaries-romania-2026/` |
| 9 | it salaries romania 2026 | en | 33 | 38 | `/blog/it-salaries-romania-inflation-2026/` |
| 10 | recrutare ai romania | ro | 77 | 85 | `/blog/` |
| 11 | salarii it romania 2026 | ro | 86 | 96 | `/blog/it-salaries-romania-inflation-2026/` |
| 12 | salarii it romania inflatie | ro | 98 | 109 | `/blog/it-salaries-romania-inflation-2026/` |

`rank` = rank_group (organic position). `abs` = rank_absolute (position
including SERP features).

### Not ranking in top 100

`it recruitment romania` · `headhunting romania` (en + ro) · `recrutare it
romania` · `ats friendly cv` · `cv optimizat pentru ats` · `eu ai act
recruitment` · `agentie de recrutare it` · `salarii it romania` ·
`ai technical screening` · `applied ai engineer` · `ai native engineering` ·
`ai resume screening reliability` · `it recruitment romania 2026` ·
`recrutare it timisoara` · `romania it recruitment agency engineers`

`recruitment agency timisoara` failed with API error 40101 on three attempts
and was not measured.

---

## Reading of the profile

### The local pack is won

`it recruitment agency timisoara` at #1 and `agentie recrutare it timisoara`
at #3 both land on the homepage. Geographic + service queries are working in
both languages. Note both SERPs are thin (18 and 123 results) — low
competition, but that is still the money query for a Timișoara agency.

### Content ranks; the category term does not

Blog posts hold positions 2, 5, 11, 19. But the head terms — `it recruitment
romania`, `recrutare it romania`, `headhunting romania` — return nothing in
the top 100. The site ranks for specific, long-tail, dated content and is
absent on the broad category. That is a normal profile for a young domain
and the gap is where the growth is.

### Romanian content is ranking — a correction

The AI visibility report I produced earlier stated the site was English-only.
That was wrong: `/ro/` carries a full parallel tree with 14 translated posts,
and `/ro/blog/it-salaries-romania-inflation-2026-ro/` ranks **#10** for
`salarii it romania inflatie`. The Romanian tree works when it surfaces.

The problem is narrower than "no Romanian content": on `site:wise-step.ro`
only `/ro/` and `/ro/services/` appear — none of the 14 `/ro/blog/` posts
show in the index sample. So one Romanian post ranks #10 while the rest of
the Romanian blog appears not to be indexed.

### Language cannibalization

On `salarii it romania inflatie` — a Romanian-language query — **both**
versions rank: the Romanian page at #10 and the English page at #98. On
`salarii it romania 2026` only the English page ranks, at #86. Google is
choosing between the two versions inconsistently, which points at hreflang
not being read correctly.

### The blog index outranks the posts

`/blog/` ranks for `ai recruitment agency romania` (#17) and `recrutare ai
romania` (#77) instead of the relevant post. A listing page ranking in place
of the article usually means the article's on-page targeting is too weak for
Google to pick it.

---

## Recommended actions

1. **Fix hreflang between `/` and `/ro/`.** Two versions competing on one
   Romanian query, and inconsistent selection across similar queries. Verify
   reciprocal `hreflang="ro"` / `hreflang="en"` plus `x-default`.

2. **Get `/ro/blog/` indexed.** 14 posts, effectively none visible in the
   index sample, while the one that does rank sits at #10. Submit the
   Romanian URLs, check for `noindex`, and confirm they are in
   `sitemap-0.xml` (they are) and reachable via internal links from `/ro/`.

3. **Build a page for the category head terms.** `it recruitment romania`
   and `recrutare it romania` have no wise-step.ro presence in the top 100.
   `/services/` is the natural target and currently does not compete.

4. **Strengthen the AI-recruitment posts.** `/blog/` outranking the specific
   posts on AI recruitment queries means the posts are not signalling their
   own topic clearly enough — titles, H1, and internal anchors.

5. **Defend the Timișoara queries.** #1 and #3 on thin SERPs is a position
   worth protecting: local schema, GBP consistency, and a dedicated location
   section on the homepage.

---

## Methodology

| Call | Purpose | Cost |
|---|---|---|
| `dataforseo_labs/google/ranked_keywords/live` | database lookup, RO | $0.012 |
| `dataforseo_labs/google/domain_rank_overview/live` × 4 | coverage check + peer control | $0.048 |
| `serp/google/organic/live/advanced` × 32 | live rank verification, 26 keywords + retries | $0.332 |
| `serp/google/organic/live/advanced` — `site:` query | index sample | $0.018 |
| **Total** | | **$0.50** |

Balance after run: $46.03.

**Confidence.** Rankings listed: high — each is a live SERP fetch with the
URL matched in the result set. Absences: medium — a keyword absent from the
top 100 at one point in time on desktop in one location; mobile, personalized,
and other locales were not checked. Index coverage: medium — `site:` queries
approximate the index rather than reporting it; Search Console would settle
whether the `/ro/blog/` posts are genuinely unindexed.

**Not covered:** search volume and traffic estimates for these keywords —
Labs has no data for this domain, so volume would need Keyword Planner or a
separate `keywords_data` call.
