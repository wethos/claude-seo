# Content Quality / E-E-A-T Analysis — https://wise-step.ro/ (Homepage)

**Date:** 2026-08-14
**Method:** Fetched via `render_page.py --mode auto` (raw HTML, no SPA shell detected, HTTP 200, no redirects). Full HTML parsed with `parse_html.py` + trafilatura for boilerplate-stripped body text. Page reachable, not paywalled, well above the 100-word retrieval threshold — normal analysis path applies.

---

## Content Quality Score: 54/100

## Who / How / Why Heuristic

| Check | Result |
|---|---|
| **Who** | Identifiable business entity (Wise Step Recruiting SRL, Timișoara, RO, founded 2021) with schema-level contact detail — but **zero named individuals** (no founder/recruiter names, titles, photos, or credentials) anywhere on the homepage. Weak personal accountability signal. |
| **How** | Copy reads as human-authored, brand-specific marketing language (not generic/templated AI filler); uses concrete industry terms (Cloud & DevOps, Data & AI). No factual-accuracy red flags detected. Passes. |
| **Why** | Purpose is transparent — B2B lead generation for recruiting services, disclosed via clear CTAs ("Get in Touch," "Start a Conversation"). Not deceptive, not thin/ad-only. Passes. |

Net: passes "How" and "Why" cleanly; **fails "Who"** at the individual-accountability level, which under Sept 2025 QRG is a meaningful E-E-A-T drag for a services business where buyers are evaluating who they'd actually work with.

---

## E-E-A-T Breakdown (this skill's weighting)

| Factor | Weight | Score | Notes |
|---|---|---|---|
| **Experience** | 20% | **12/20** | Genuine but generic first-person claims ("former software engineers," "15+ years," "we've written the code, led the teams, shipped the products"). No named case studies, no quantified outcomes. One stat block ("Tech Practitioners") renders with **no actual number** — looks like a broken/placeholder metric, which undercuts authenticity. |
| **Expertise** | 25% | **13/25** | Domain specificity exists (Cloud & DevOps, Data & AI, Software Engineering, Technical Leadership; Java/Python/Kubernetes/Spark named in FAQ schema), but nothing on the page demonstrates expertise via credentialed individuals, methodology detail, or published proof. Claims are asserted, not shown. |
| **Authoritativeness** | 25% | **13/25** | `sameAs` links to LinkedIn company page, The Manifest, and RocketReach; a Clutch reviews widget references 6 specific review IDs. Moderate third-party validation for a small agency, but no press coverage, awards, or citable external authority, and the Clutch reviews are **not rendered as text** (JS-widget only). |
| **Trustworthiness** | 30% | **21/30** | Strong technical trust baseline: HTTPS via Cloudflare with proper security headers (X-Frame-Options, Permissions-Policy, Referrer-Policy), Privacy Policy + Terms linked, ANPC SAL/SOL EU dispute-resolution links (real compliance signal for a RO/EU business), Organization schema with email/phone/founding date. Held back by an **address with no street-level detail** (city/region/country only) and no named human contacts. |
| **Total** | 100% | **59/100** | |

---

## Content Metrics

| Metric | Value | Benchmark | Status |
|---|---|---|---|
| Word count (trafilatura, boilerplate-stripped) | 282 words | 500-word homepage floor (coverage floor, not a target) | **Below floor** — 56% of coverage floor |
| Word count (raw DOM incl. nav/footer, `parse_html.py`) | 355 words | — | for reference only |
| Flesch Reading Ease (manual calc, proxy metric only) | 62.2 | "Plain English," ~8th–9th grade | Good — accessible, not a ranking factor |
| Avg. words/sentence | 10.8 | — | Short, scannable |
| H1 | 1 ("Fast-Track Your Tech Talent.") | 1 recommended | Good |
| H2 / H3 | 4 / 3 | — | Clean hierarchy |
| Keyword usage | "tech talent," "recruit(ing)," "hire/hiring," "engineers" appear naturally, no stuffing | — | Natural |
| Location keywords in visible body | "Timișoara" appears **nowhere** in visible copy; "IT Recruitment · Romania" appears once in a small hero eyebrow label only | — | Weak reinforcement outside metadata/schema |
| Internal links | About, Services, Jobs, Blog, Contact (nav + footer, duplicated) | — | Adequate |
| External links | ANPC/EU ODR only (legally required, nofollow) | — | No editorial external citations (normal for a homepage) |
| Multimedia | Decorative SVGs/CSS only; no photos of team, office, or clients; testimonials load via third-party Clutch JS widget with no static fallback | — | Weak |
| Structured data | Organization+ProfessionalService, WebSite, FAQPage (3 valid JSON-LD blocks) | — | Strong breadth, but see FAQ issue below |

---

## AI Citation Readiness: 65/100

| Signal | Score | Notes |
|---|---|---|
| Structured data breadth/quality | 25/30 | Organization, WebSite, FAQPage all valid and well-formed. |
| Quotable facts in visible text | 12/20 | A few citable claims ("15+ years," "former software engineers") but no quantified proof points (placements, retention, time-to-hire). |
| Heading hierarchy/scannability | 16/20 | Single H1, logical H2/H3 structure. |
| Answer-first / visible Q&A formatting | 8/15 | **FAQPage JSON-LD exists only in `<script>` in `<head>` — the four Q&A pairs are not rendered anywhere in the visible DOM.** This is invisible to plain-text extraction and violates Google's structured-data policy that markup must reflect on-page content. |
| Freshness signals | 4/15 | No visible "last updated" indicator; detected `publication_date` (2026-01-01) is almost certainly picked up from the footer's `© 2026` copyright string rather than a real content date — unreliable signal. |

---

## Content Freshness

- No visible last-updated/dateModified indicator on the page.
- Detected `publication_date` (2026-01-01) is very likely a false positive from the footer copyright year, not a genuine freshness signal.
- Organization schema `foundingDate` (2021-01-01) reflects company age, not content recency.

---

## Issues Found

1. **Thin homepage body content** — 282 words of substantive copy vs. the 500-word topical-coverage floor for homepages.
2. **Broken/placeholder stat** — the middle stats-block item shows the text "Tech Practitioners" in place of an actual number, with an empty label; reads as an unfinished component rather than real data.
3. **Hidden FAQPage schema** — 4 Q&A pairs marked up in JSON-LD are never rendered in the visible page, risking rich-result ineligibility and invisible to non-JS-executing text extractors.
4. **No named individuals** — no founder/recruiter names, titles, photos, or credentials anywhere on the homepage.
5. **JS-only testimonials** — Clutch review widget has no static text fallback; content is invisible to crawlers/LLMs that don't execute the third-party widget script.
6. **Incomplete address** — schema `PostalAddress` has city/region/country only, no street address.
7. **Unreliable freshness signal** — apparent publication date is likely a copyright-year artifact, not a true content date.
8. **No quantified experience proof** — claims ("15+ years," "exceptional and fast results") are qualitative only, with zero specific metrics.
9. **Weak geographic reinforcement** — "Timișoara"/"Romania" live in metadata/schema and one small hero label but aren't reinforced in the visible body copy.

## Recommendations

1. Expand homepage copy toward the 500-word floor with real topical coverage: a short "how we work" process section, a named-leadership blurb, and 2–3 concrete outcome metrics.
2. Fix the broken stats block — show an actual number for "Tech Practitioners" or replace it with a real quantified metric.
3. Bring the FAQ into parity: render the same Q&A text visibly on the page (recommended), or remove the FAQPage schema until visible content matches it.
4. Add named team members (founder/recruiters) with photos, titles, and LinkedIn links — this is the single highest-leverage fix for the weak "Who" signal.
5. Add a static 2–3 quote testimonial fallback in the HTML alongside the Clutch widget so review content is crawlable without JS.
6. Add a full street-level address (or a Google Business Profile link) to strengthen local trust/NAP consistency.
7. Add a genuine, intentional "last updated" signal (visible text and/or `dateModified` in schema) rather than relying on the footer copyright year.
8. Reinforce "IT recruitment," "Timișoara," and "Romania" once or twice more in visible body paragraphs, not just title/meta/eyebrow.
9. Add 2–3 quantified proof points (e.g., placements made, average shortlist time, retention rate) to convert qualitative experience claims into verifiable ones.
