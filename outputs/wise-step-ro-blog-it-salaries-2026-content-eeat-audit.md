# Content Quality Analysis: wise-step.ro/blog/it-salaries-romania-2026/

**Date:** 2026-08-14
**Method:** Fetched via `render_page.py` (raw mode, no SPA detected, HTTP 200) and parsed with `parse_html.py` + `trafilatura`.

---

## Who / How / Why Heuristic (Google QRG)

| Test | Finding | Verdict |
|---|---|---|
| **Who** created this? | Named author "Calin Muresan," visible byline on-page, linked in `BlogPosting` schema to `/about/` and a real LinkedIn profile (`sameAs`). Publisher is a registered `Organization`/`ProfessionalService` (Wise Step Recruiting, Timișoara, RO) with NAP, phone, email in sitewide schema. | Pass — real, identifiable author and publisher |
| **How** was it made? | Blends first-hand recruiter commentary ("we work with these figures daily," "15 years of hands-on experience") with six named third-party datasets (INS, eJobs/Salario, NewTech Academy, Brainspotting, Paylab, HackingWork), each with a stated reference period. | Partial pass — sources are *named* but **zero are hyperlinked**, breaking the verification trail |
| **Why** was it made? | Primary intent: help candidates/employers benchmark IT comp. Secondary/commercial intent: lead-gen for Wise Step's recruitment services, clearly siloed into its own "How Wise Step can help" section rather than interwoven into the data. | Pass — commercial intent is transparent, not deceptive |

---

## E-E-A-T Breakdown

| Factor | Weight | Score | Key Signals |
|---|---|---|---|
| **Experience** | /20 | **15** | Strong practitioner framing ("salary data isn't academic for us," recruiter-specific implications section). No individual case studies, no proprietary placement data, no in-article author photo/first-person narrative beyond the company "we." |
| **Expertise** | /25 | **18** | Author has a real, linked LinkedIn identity; publisher specializes in IT recruitment; content shows accurate, granular technical/market fluency (stacks, seniority bands, city nuance). Gap: no inline author bio/title near the byline (credentials live only on `/about/`, one click removed). |
| **Authoritativeness** | /25 | **15** | Six named, dated data sources cited by name. Undermined by **zero outbound citation links** to any primary source (INS, eJobs, Paylab, etc.), and no external recognition/press signals surfaced within the article itself. |
| **Trustworthiness** | /30 | **20** | HTTPS, Organization schema with NAP/phone/email, Privacy Policy + Terms linked in footer, transparent commercial framing, precise (non-vague) figures. Undermined by a **schema/body freshness mismatch** (see Freshness below) and no disclosed methodology (mean vs. median, sample size, EUR/RON conversion rate used). |
| **Total E-E-A-T** | 100 | **68/100** | |

---

## Content Quality Score: 70/100

Blends the E-E-A-T score with structural/metrics factors below — strong schema and answer-first structure partially offset by zero in-article multimedia and an uncited source trail on YMYL-adjacent numeric claims.

## Content Metrics

| Metric | Finding | Assessment |
|---|---|---|
| Word count | ~1,650–1,700 words (parsed: 1,707 incl. nav/footer; trafilatura body: ~1,560) | Passes the 1,500-word blog floor (topical-coverage floor, not a target) |
| Readability (Flesch, proxy only) | ≈ 42.8 (approx. "difficult" / college level), avg. 16.9 words/sentence | Expected for a numbers/table-dense piece; could simplify prose sections for broader accessibility — not a ranking factor, informational only |
| Heading hierarchy | 1× H1, 8× H2, 17× H3 | Strong, logical hierarchy; good for both users and chunked AI retrieval |
| Keyword usage | "IT salaries Romania [2026]" and variants appear naturally across headings/body, no stuffing detected | Natural |
| Structure | 3 comparison tables (programming roles, infra/DevOps, data/UX), seniority tiers, city breakdown, FAQ block | Well-organized |
| Multimedia | **0 in-article images, charts, or graphics** — the only 2 images site-wide are unrelated ANPC dispute-resolution logos in the footer | Gap, notable for a salary-comparison post that would benefit from a chart |
| Internal links | 16 total, but only **1 contextual in-body link** (to a related inflation/salary post); rest are nav/footer boilerplate | Thin contextual internal linking |
| External links | **2 total, both nofollow footer boilerplate** (ANPC/EC dispute resolution) — **0 links to the 6 named data sources** | Significant gap for YMYL-adjacent sourcing |

---

## AI Citation Readiness: 78/100

| Signal | Status |
|---|---|
| Quotable statistics | Excellent — precise, extractable figures throughout (e.g., "11,957 RON (June 2025) → 12,931 RON (November 2025)"; "C++ Developer 18,654 RON") |
| Structured data | `BlogPosting`, `BreadcrumbList`, and `FAQPage` (5 Q&A pairs) all present and valid — Article-type schema as expected for a blog post |
| Answer-first formatting | Strong — e.g., "The short answer: 11,000–13,000 RON net per month..." immediately follows the primary H2 |
| Heading hierarchy for chunking | Strong (8 H2 / 17 H3) |
| Tables | Present but plain HTML — **not marked up as `Table`/`Dataset` schema**, a missed structured-data opportunity |
| Citation trail for AI verification | Weak — sources named in prose but not hyperlinked, limiting AI systems' ability to trace/verify claims independently |
| Per-stat dating | Only one blanket "Last updated" disclosure at the very end; mid-article stats lack individual "as of" tags, risking stale-looking snippets if extracted out of context |

---

## Content Freshness

| Signal | Value |
|---|---|
| `datePublished` (schema + meta) | 2026-04-20 |
| `dateModified` (schema) | 2026-04-20 — **identical to datePublished** |
| Visible in-body freshness claim | "Last updated: August 2026" |
| **Inconsistency flagged** | The body text claims an August 2026 update, but `dateModified` in the `BlogPosting` JSON-LD was never bumped — this is a real freshness signal mismatch that both search engines and LLMs may read inconsistently (structured data still reads as never-updated since publication) |
| Salary-figure dating | Good — individual data points reference specific vintages inline (June 2025, November 2025, "January 2026 data," H1 2026, October 2025 comparisons) |
| Source disclosure | Present and specific: INS (Romanian National Institute of Statistics), eJobs/Salario H1 2026, NewTech Academy IT Salary Radar (Jan 2026), Brainspotting 2025, Paylab Romania, HackingWork — named but not hyperlinked |

---

## Issues Found

1. **`dateModified` schema not synced with the visible "Last updated: August 2026" claim** — stuck at the original `datePublished` (2026-04-20). This is a trust/freshness inconsistency for a salary-data page, where staleness materially affects usefulness.
2. **Zero hyperlinked citations** to any of the 6 named salary-data sources — a meaningful authoritativeness and AI-verifiability gap for YMYL-adjacent numeric claims.
3. **No multimedia in the article body** — a salary/comparison post with three data tables and no accompanying chart or visual is a missed engagement and comprehension opportunity.
4. **No inline author bio/credentials near the byline** — credentials exist but require a click to `/about/`; Google's guidance favors visible expertise signals adjacent to the content itself.
5. **No disclosed methodology** — unclear whether figures are means or medians, what sample sizes underlie them, or what RON→EUR conversion rate was used for the parenthetical EUR figures.
6. **Thin contextual internal linking** — only one in-body contextual link; the rest of the 16 internal links are template navigation/footer.
7. **Data tables use plain HTML, not `Table`/`Dataset` schema** — a missed structured-data opportunity for a numbers-heavy page.

## Recommendations

1. Update `dateModified` in the `BlogPosting` JSON-LD to match the actual last-edit date, and keep the two in sync going forward.
2. Hyperlink each named data source at first mention and in the closing "Data sources" line (INS, eJobs/Salario, NewTech Academy, Brainspotting, Paylab, HackingWork) to build a traceable citation chain for both human fact-checking and AI verification.
3. Add at least one chart/visualization (e.g., seniority-tier salary bands, city comparison) to break up the table-heavy body and strengthen the "Experience"/"multimedia" signal.
4. Add a 1–2 sentence author credential line directly under the byline (title/role at Wise Step, years of recruiting experience) rather than relying solely on the linked `/about/` page.
5. Disclose methodology briefly (e.g., "figures are medians reported net of tax; EUR conversion at X RON/EUR") to shore up Trustworthiness for YMYL-adjacent compensation data.
6. Mark up the three salary tables with `Table` (or a lightweight `Dataset`) schema to improve machine-readability and AI Overview extraction fidelity.
7. Add 2–3 more contextual internal links from within the body (e.g., to `/services/` for the hiring-focused sections, or to other salary/market posts) beyond the single existing cross-link.
