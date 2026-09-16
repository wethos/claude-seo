# Technical SEO Audit — https://wise-step.ro

**Audit date:** 2026-08-14
**Site:** Astro-built static site (SSR/SSG), Cloudflare-fronted, bilingual (EN default + `/ro/`)

## Technical Score: 73/100

## Category Breakdown

| # | Category | Status | Score |
|---|----------|--------|-------|
| 1 | Crawlability | Warn | 80/100 |
| 2 | Indexability | Warn | 75/100 |
| 3 | Security | Warn | 65/100 |
| 4 | URL Structure | Pass | 90/100 |
| 5 | Mobile | Pass | 85/100 |
| 6 | Core Web Vitals | Warn | 70/100 |
| 7 | Structured Data | Warn | 70/100 |
| 8 | JS Rendering | Pass | 90/100 |
| 9 | IndexNow | Fail | 0/100 |

---

## Critical Issues

**1. 6 of 9 live JobPosting pages have expired `validThrough` dates but still return HTTP 200 with unexpired-looking markup.** Checked all job pages in the sitemap:

| URL | HTTP | `validThrough` |
|---|---|---|
| `/jobs/senior-data-engineer/` | 200 | 2026-06-30 (expired 45 days ago) |
| `/jobs/performance-engineer/` | 200 | 2026-07-03 (expired) |
| `/jobs/data-architect/` | 200 | 2026-07-04 (expired) |
| `/jobs/ml-engineer-databricks/` | 200 | 2026-07-04 (expired) |
| `/jobs/business-analyst-rpa-uipath/` | 200 | 2026-07-23 (expired) |
| `/jobs/rpa-developer-uipath/` | 200 | 2026-07-23 (expired) |
| `/jobs/general-ledger-accountant-timisoara/` | 200 | 2026-08-12 (expired 2 days ago) |
| `/jobs/head-of-production-mechanics/` | 200 | 2026-08-24 (not yet expired) |
| `/jobs/erp_specialist/` | 200 | 2026-09-15 (not yet expired) |

Google's structured-data guidelines require expired job postings to return `404`/`410`, be removed from JobPosting markup, or be updated with a new `validThrough` — otherwise "Google may trust your job posting markup less," which can suppress Google for Jobs eligibility site-wide. Recommendation: add a CI/cron check that flips expired postings to `noindex` + HTTP 410, or removes the JobPosting block, or auto-refreshes `validThrough` from the ATS.

**2. AI-crawler access in robots.txt is internally contradictory.** Full file fetched:
```
# BEGIN Cloudflare Managed content
User-agent: ClaudeBot
Disallow: /
User-agent: Google-Extended
Disallow: /
User-agent: GPTBot
Disallow: /
...
# END Cloudflare Managed Content

# Allow AI search/inference crawlers
User-agent: GPTBot
Allow: /
User-agent: ClaudeBot
Allow: /
User-agent: Google-Extended
Allow: /
```
The same user-agent tokens (`GPTBot`, `ClaudeBot`, `Google-Extended`) appear in two separate groups with opposite rules. Per RFC 9309 §2.2.1, records for the same user-agent across multiple groups must be combined; both path rules here are `/` (equal specificity), so outcome on the tie is parser-dependent — Google's documented tie-break is "least restrictive wins" (Allow), but this is not a universal guarantee across GPTBot's/ClaudeBot's own parsers. Worse, this pattern is characteristic of Cloudflare's "Block AI Bots" WAF managed rule auto-injecting a Disallow block on every deploy — if that Cloudflare Bot Management toggle is also active at the network layer, it will hard-block these bots regardless of what the custom Allow rules say, silently defeating the site's intended GEO/AI-visibility strategy. **Recommendation:** consolidate to one group per user-agent, and separately verify in the Cloudflare dashboard whether "AI Scrapers and Crawlers" bot blocking is enabled — if so, disable it or add explicit bypass rules for GPTBot/ClaudeBot/PerplexityBot/Google-Extended, since robots.txt alone won't override an edge WAF block.

---

## High Priority Issues

**3. Homepage has no hreflang annotations, while inner pages do.** `/about/`, `/ro/about/`, and job pages all correctly emit reciprocal, self-referencing hreflang:
```html
<link rel="alternate" hreflang="en" href="https://wise-step.ro/about/">
<link rel="alternate" hreflang="ro" href="https://wise-step.ro/ro/about/">
<link rel="alternate" hreflang="x-default" href="https://wise-step.ro/about/">
```
But `https://wise-step.ro/` (EN home) has **zero** `<link rel="alternate">` tags despite the homepage's own JSON-LD declaring `"inLanguage": ["ro", "en"]` and `https://wise-step.ro/ro/` existing as a full parallel version. This is likely a template bug specific to the index route (Astro `index.astro` not inheriting the hreflang partial used elsewhere). Given the scope, defer full validation to the `seo-hreflang` sub-skill, but flag this specific homepage gap as a quick, high-value fix — it's the single most-linked, most-crawled URL on the domain.

**4. No `Strict-Transport-Security` (HSTS) header.** Confirmed via `curl -D -` on both `/` and `/jobs/senior-data-engineer/` — headers present are `x-frame-options`, `x-content-type-options`, `referrer-policy`, `permissions-policy`, but no `strict-transport-security` at all. Site is Cloudflare-fronted, so this is a one-toggle fix (SSL/TLS → Edge Certificates → "Always Use HTTPS" + HSTS) or set at origin. Without it, users are vulnerable to SSL-stripping on first visit/typed `http://` URLs before the 301 redirect executes.

**5. No `Content-Security-Policy` header anywhere checked.** No CSP or `Content-Security-Policy-Report-Only` on homepage or job pages. Site loads third-party scripts (`googletagmanager.com`, `widget.clutch.co`, Google Fonts) with no CSP allow-list — this is both a security gap (XSS blast-radius) and a missed opportunity to harden `frame-ancestors` beyond the existing `X-Frame-Options: SAMEORIGIN`.

---

## Medium Priority Issues

**6. FAQPage JSON-LD unlikely to earn rich results.** The homepage's `FAQPage` markup (4 Q&As, valid schema) is technically well-formed, but Google restricted the FAQ rich-result SERP feature (since 2023) to a narrow set of authoritative government/health sites. For a commercial recruiting agency this markup is very unlikely to render as a SERP rich snippet in classic Google Search — it still has value for AI answer engines/GEO (ChatGPT, Perplexity, AI Overviews commonly lift FAQ blocks), so keep it, but don't expect classic SERP FAQ snippets.

**7. Duplicate brand name in inner-page `<title>` tags.** `/about/` → `About — Wise Step Recruiting | Wise Step Recruiting` and `/jobs/` → `Jobs — Wise Step Recruiting | Wise Step Recruiting`. The brand name is concatenated twice (once by the page template, once by a global suffix), wasting pixel width in SERPs and diluting the primary keyword signal.

**8. Inconsistent slug casing: `erp_specialist` uses underscores** while every other job slug (`business-analyst-rpa-uipath`, `data-architect`, `general-ledger-accountant-timisoara`, `head-of-production-mechanics`, `ml-engineer-databricks`, `performance-engineer`, `rpa-developer-uipath`, `senior-data-engineer`) uses hyphens. Underscores are treated as word-joiners rather than separators by Google — rename to `erp-specialist` and 301-redirect the old slug.

**9. Hero LCP content is JS-gated via inline styles.** Homepage `<h1>`, subhead, tagline, body copy, and CTAs all ship with `style="opacity:0;transform:translateY(30px)"` (or `opacity:0` alone), only becoming visible once an `IntersectionObserver`/scroll-reveal script runs client-side. The text is present in the raw HTML (confirmed via `render_page.py`, `mode_used: raw`, `is_spa:false`) so it isn't a crawlability problem, but it is a real Core Web Vitals / perceived-performance risk: if that JS is delayed, blocked by an ad-blocker/privacy extension, or throws an error, the hero — almost certainly the LCP element — stays invisible indefinitely. No `<noscript>` or CSS-only (`@media (prefers-reduced-motion)`/animation-fallback) safety net was found. Recommend converting to a CSS `@keyframes`/`animation-fill-mode` approach that defaults to visible, or adding a `no-js` class fallback.

**10. IndexNow not implemented.** No key file found at `/indexnow.txt`, `/IndexNow.txt`, or `/.well-known/indexnow.txt` (all 404), and no reference to IndexNow in robots.txt or page `<head>`. Given the site publishes/updates blog and job content regularly, adding IndexNow (Bing, Yandex adoption; low effort) would speed up Bing/Yandex indexing of new job postings and blog posts. Use `scripts/indexnow_submit.py` once a key file is generated and hosted at the domain root.

**11. Stray `X-Robots-Tag: ai-input=yes` line inside robots.txt.** This sits after the AI-crawler Allow/Disallow rules and before the `Sitemap:` line. `X-Robots-Tag` is an HTTP response header directive, not a robots.txt token — parsers will ignore it silently, so if the intent was to signal AI-input permission per the Content-Signal spec, it's not taking effect anywhere. (Note: the file does correctly use `Content-Signal: search=yes,ai-train=no,use=reference` as an actual robots.txt directive near the top, which is valid and current per the IETF Content Signals proposal — that part works; the stray `X-Robots-Tag` line does not.)

---

## Low Priority Issues

**12. `Access-Control-Allow-Origin: *` on the HTML document response itself** (not just APIs/fonts) — harmless for a public marketing page but non-standard; verify this isn't an unintended blanket CORS policy from a Cloudflare Worker/Transform Rule.

**13. Third-party Clutch reviews widget** (`https://widget.clutch.co/static/js/widget.js`, loaded `async`) adds an uncontrolled layout injection into the homepage; `data-height="300"` is set which should reserve space and limit CLS, but it's worth spot-checking in real Chrome DevTools since it's a common CLS offender on marketing sites.

---

## What's Working Well

- **Sitemap**: `robots.txt` → `Sitemap: https://wise-step.ro/sitemap-index.xml` → HTTP 200, valid `sitemapindex` → child `sitemap-0.xml` → HTTP 200, valid, contains EN + RO URL sets with trailing-slash consistency.
- **Redirects**: `http://` → `https://` (301, single hop), `https://www.` → apex (301, single hop), no-trailing-slash → trailing-slash (308) — all clean, no chains >1 hop.
- **JS rendering**: `render_page.py --mode auto` resolved via raw fetch (`mode_used: "raw"`, `is_spa: false`) — full text content, meta tags, and JSON-LD are present in the initial HTML response (Astro static output). JS is used only for progressive enhancement (mobile nav, scroll reveals, cookie-gated GA4, language switcher), not for core content delivery.
- **Structured data breadth**: valid Organization/ProfessionalService, WebSite, FAQPage on the homepage, and JobPosting with all Google-required properties (`title`, `description`, `datePosted`, `validThrough`, `employmentType`, `hiringOrganization`, `jobLocation`) on job pages — the *fields* are correct, only the expiry-hygiene process (Critical Issue #1) needs fixing.
- **Canonical tags**: self-referencing and correct on every page checked (`/`, `/about/`, `/ro/about/`, `/jobs/`, `/jobs/senior-data-engineer/`, blog post).
- **Security headers present**: `X-Content-Type-Options: nosniff`, `X-Frame-Options: SAMEORIGIN`, `Referrer-Policy: strict-origin-when-cross-origin`, `Permissions-Policy: camera=(), microphone=(), geolocation=(), interest-cohort=()`.
- **Mobile**: correct `viewport` meta, responsive `@media (max-width:768px)` breakpoints with working hamburger nav, no intrusive interstitials found.
- **Mixed content**: none found — no `http://` sub-resource references in the fetched homepage HTML.
- **Fonts**: `preload` + `onload` swap pattern used for Google Fonts, avoiding render-blocking `@import`/synchronous stylesheet loads.

---

## Notes / Data Gaps

- **PSI/CrUX field data unavailable this run** — `pagespeed_check.py` returned `"PSI rate limit exceeded (240 QPM / 25,000 QPD)"`. The Core Web Vitals score above (70/100) is lab/source-based reasoning only (see Issue #9 and the fonts/third-party-script notes) — re-run `"$HOME/.claude/skills/seo/bin/claude-seo" run pagespeed_check.py https://wise-step.ro --json` later for real LCP/INP/CLS field data to replace this estimate.
- Detailed hreflang cross-validation (all EN/RO URL pairs, not just `/about/`) was spot-checked only, not exhaustively — for full coverage run the `seo-hreflang` sub-skill.
- Structured-data property-level validation (e.g., FAQPage answer length limits) was reviewed against publicly known Google guidelines, not run through the Rich Results Test API — recommend a pass with `seo-schema` for machine validation.

## Files referenced
No local files were created for this audit; all data was gathered live via:
- `"$HOME/.claude/skills/seo/bin/claude-seo" run sitemap_discovery.py https://wise-step.ro --json`
- `"$HOME/.claude/skills/seo/bin/claude-seo" run render_page.py https://wise-step.ro --mode auto --json`
- `"$HOME/.claude/skills/seo/bin/claude-seo" run pagespeed_check.py https://wise-step.ro --json` (rate-limited)
- `curl` against `/`, `/robots.txt`, `/sitemap-index.xml`, `/sitemap-0.xml`, `/about/`, `/ro/`, `/ro/about/`, `/jobs/`, `/jobs/*` (9 postings), `/blog/ai-native-engineering/`, `http://`, `https://www.`
