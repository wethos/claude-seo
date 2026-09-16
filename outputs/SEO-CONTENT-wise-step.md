# Content Quality & E-E-A-T Analysis — wise-step.ro

**Analyzed:** 2026-08-21 · homepage, `/about/`, `/blog/it-salaries-romania-2026/`
**Scores below are this skill's heuristics, not Google-internal signals.** No third-party tool has access to Google's ranking data. Validate against Search Console as the first-party source.

---

## Content Quality Score: 57/100

The site has two quality tiers. **Blog posts are well built** — Person schema with LinkedIn `sameAs`, BreadcrumbList, BlogPosting, real tables, 16 internal links. **The money pages are not.** The homepage is 355 words, names nobody, carries no verifiable claim, and its single strongest trust asset is invisible to every crawler and assistant.

### E-E-A-T Breakdown

| Factor | Score | Key signals |
|---|---|---|
| Experience | 11/20 | Founders' engineering background stated on `/about/` with specifics. No case studies anywhere; the 7 named clients in your own `features.md` appear nowhere on the site. Homepage asserts "former software engineers" with zero supporting evidence. |
| Expertise | 17/25 | Strong on blog: `Person` schema, named author, LinkedIn `sameAs`. Weak on money pages: homepage names no one, no `Person` schema outside blog posts, and the credential itself contradicts across pages. |
| Authoritativeness | 10/25 | Clutch 5.0 / 7 reviews — **rendered by a JS widget, invisible in HTML**. Clutch is missing from `sameAs`. `sameAs` carries LinkedIn, TheManifest, RocketReach only. |
| Trustworthiness | 19/30 | HTTPS, privacy, terms, ANPC/SOL consumer compliance all present. Undercut by an empty testimonial block, a counter reading "0", NAP that exists only in schema, and FAQ schema whose answers are not on the page. |

*Weights follow Google's stated hierarchy — trust most important (30), expertise/authoritativeness (25 each), experience (20). Google publishes no numeric weights; this split is our internal model.*

### AI Citation Readiness: 42/100 (homepage) · 71/100 (blog posts)

Homepage gives an assistant nothing to quote. 355 words, no statistic that survives scrutiny, no answer-first structure, and no link into the 10 published posts. `Organization` schema is solid and does real entity work — that is most of the 42.

---

## Google's Who / How / Why Test

| Question | Homepage | Blog |
|---|---|---|
| **Who** created it? | ✗ Fails. No byline, no names, no `Person` schema. Founders are named only on `/about/`. | ✓ Passes. Calin Muresan, `Person` schema, LinkedIn `sameAs`, author URL. |
| **How** was it created? | ✗ No process disclosure, no evidence of first-hand work. | ~ Partial. Real tables and structure, but only 2 external citations across a 3-table salary guide. |
| **Why** does it exist? | ~ Reads as positioning copy, not help. Nothing a buyer can act on. | ✓ Genuinely useful reference content. |

---

## Critical Issues

### 1. Clutch reviews are invisible to Google and every AI assistant
```html
<div class="clutch-widget" data-clutchcompany-id="2122333"
     data-reviews="359803,250217,199400,199354,198875,198709"
     data-url="https://widget.clutch.co" data-widget-type="8"></div>
```
The section renders as an `<h2>` — "What our clients say." — followed by an empty div. Your strongest authority asset (5.0 rating, 7 reviews, 7 named enterprise clients including TRW Automotive, Tremend, HTEC Group, Plastic Omnium) contributes **nothing** to E-E-A-T, nothing to AI citation, and nothing to a visitor with the widget blocked.

**Fix:** render the verbatim quotes as real HTML — attributed by role and company, exactly as they sit in `features.md`. Keep the widget below them if you want the Clutch branding. Add `Review`/`AggregateRating` schema only for reviews genuinely displayed on the page. Add the Clutch profile URL to `sameAs`.

### 2. FAQPage schema whose answers are not on the page
Four Q&A pairs are in JSON-LD. None of the text appears in the rendered HTML. Google's structured data policy requires marked-up content to be visible to users — this is the kind of mismatch that draws a manual action. Compounding it: FAQPage no longer produces FAQ rich results for most sites, so the risk buys nothing.

**Fix:** publish the four questions as a visible FAQ block on the homepage — they are good, buyer-shaped questions — or drop the schema. Do not keep schema-only.

### 3. The homepage tells crawlers you have zero years of experience
```
15 + Years experience
Fast Precise placement
0 + Years Experience      ← animated counter, static value is 0
In the software industry
```
A JS counter animates to its target, but the served HTML says `0`. Googlebot, ChatGPT, and Perplexity read `0+ Years Experience`. It also sits directly beneath a hardcoded "15+ Years experience", so the page contradicts itself twice over.

**Fix:** server-render the final value; animate from it, not to it.

---

## High-Priority Issues

**4. Homepage is 355 words** — below the 500 coverage floor, and thin for a page carrying every commercial message. Not about word count as a ranking factor; there is simply not enough substance for a buyer or an assistant to work with.

**5. Zero links from homepage into the blog.** Ten posts are live. The homepage links to `/blog/` and stops. The hub passes no authority to the pillar content, and your strongest topical signals are one click further from the root than they need to be.

**6. Founders are invisible on the money pages.** Calin Muresan and Alina Nicorici are named on `/about/` with real credentials. The homepage — where the buyer lands — names nobody. No `Person` schema on either page.

**7. The core credential contradicts itself.**
- Homepage: "Over 15 years of experience", "15+ Years experience"
- `/about/`: "Two decades of hands-on software engineering"
- `features.md`: "~20 years"

Pick one figure and use it everywhere. Under a brand rule that says *every claim is backed by a number*, an inconsistent number is worse than no number.

**8. None of your hard benchmarks appear anywhere on the site.**

| Benchmark (from `features.md`) | On site? |
|---|---|
| First candidates in 10–15 days | ✗ |
| Average time to fill 28–30 days | ✗ |
| Curated shortlist of 3–5 candidates | ✗ — homepage says "No CV Floods", never the number |
| 3–6 month replacement guarantee | ✗ |
| Named clients (7, citable from Clutch) | ✗ |

This is the single largest gap in the audit. Your brand voice document says *"'40% of counter-offers' not 'amazing retention'"* — and then the homepage runs on "precision over volume", "exceptional and fast results", "genuine alignment". That is the adjective-driven register your own guidelines classify as a deal-breaker. Every number above is already verified and publishable.

**9. Salary guide is stale and says so in schema.** `datePublished` and `dateModified` are both `2026-04-20` — four months old on a page whose entire value is current salary bands, and whose refresh cycle your own notes call annual with quarterly checks. No visible last-updated date in the page text either, which `seo-guidelines.md` requires for AI authority signaling.

**10. Article image fails Google's minimum and is hotlinked.**
```
https://images.unsplash.com/photo-1554224155-6726b3ff858f?&fit=crop&w=430&h=240
```
430px wide, used as the `BlogPosting.image`. Google requires ≥1200px for article image eligibility. It is also a third-party CDN dependency on your primary content asset.

---

## Medium-Priority Issues

| # | Issue | Detail |
|---|---|---|
| 11 | Heading hierarchy skips | H2 → H4 on both homepage and `/about/`, no H3 between |
| 12 | Duplicate headings | "We speak tech" appears as H4 *and* H3 on the homepage with near-identical copy; "Hire Smarter. Move Faster." runs twice |
| 13 | NAP not visible | Timișoara address and `+40774611258` exist only in JSON-LD. Footer carries neither. Weak for local trust and for the `agentie de recrutare timisoara` intent |
| 14 | Clutch absent from `sameAs` | TheManifest and RocketReach are listed; the profile that actually holds the reviews is not |
| 15 | Salary pillar under-length for its type | 1,527 words against your own 3,000–5,000 target for comprehensive guides |
| 16 | Thin sourcing on a data page | 2 external links supporting 3 tables of salary figures, on a site whose first brand rule is that every claim is sourced |
| 17 | ANPC/SOL logos hotlinked | Served from `etamade-com.github.io` — a third-party GitHub Pages account hosting your legally-required consumer-dispute badges |
| 18 | `/about/` at 465 words | Below the 800 floor for a page doing service-page work |

---

## What's Already Right

Worth stating plainly, because the blog build is genuinely good and the fixes above should not disturb it:

- `BlogPosting` + `Person` + `BreadcrumbList` + `Organization` schema, correctly `@id`-linked
- Named author with LinkedIn `sameAs` on posts
- 16 internal links on the salary post — cluster wiring is working
- Tables used where tables belong; 8 H2 / 17 H3 structure is clean and citable
- Bilingual EN/RO published
- HTTPS, privacy, terms, ANPC/SOL compliance complete
- `Organization` schema description is specific and does real entity work
- `aria-labelledby` and skip-to-content link present — accessibility above average

---

## Recommendations, in order

1. **Render the Clutch reviews as HTML.** Biggest single E-E-A-T gain available, and the content already exists in `features.md`. Add Clutch to `sameAs`.
2. **Fix or remove the FAQ schema mismatch.** Publish the four answers on the page. Policy risk with no offsetting benefit.
3. **Server-render the "0" counter.** One-line fix telling every crawler you have zero years of experience.
4. **Put the numbers on the homepage.** 10–15 days to first candidates · 28–30 day average fill · 3–5 candidate shortlist · 3–6 month replacement guarantee. Replaces the adjective copy your own brand rules prohibit, and creates the first quotable claims on the page.
5. **Name the founders on the homepage** with `Person` schema and links to `/about/`.
6. **Reconcile 15 years vs two decades vs ~20** across site and context files.
7. **Link 3–5 pillar posts from the homepage** with descriptive anchors — salary guide, headhunting, AI/data recruitment.
8. **Refresh the salary guide**, update `dateModified`, add a visible last-updated line, and expand toward the 3,000-word target with more sourced bands.
9. **Replace the 430px Unsplash hero** with a self-hosted image ≥1200px.
10. Fix heading hierarchy, de-duplicate headings, add visible NAP to the footer, self-host the ANPC logos.

Items 1–4 are the ones that move the score. Everything after is hygiene.
