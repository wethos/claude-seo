# SCHEMA-REPORT: wise-step.ro

Analyzed 2026-08-14. **Supersedes an earlier same-day report that wrongly said "no schema found"** — that check used WebFetch's HTML→markdown conversion, which silently strips `<script>` blocks. This audit pulled raw HTML via curl and parsed the actual JSON-LD.

## Detection

Site is schema-rich, matches the inventory the user reported:

| Page | Blocks found |
|---|---|
| `/` (EN home) | `Organization`+`ProfessionalService` (combined @type), `WebSite`, `FAQPage` |
| `/ro/` (RO home) | `FAQPage` only — **Organization and WebSite are missing here** |
| `/jobs/` | `BreadcrumbList`, 9× `JobPosting` |
| `/contact/` | `BreadcrumbList`, `ContactPage`, `LocalBusiness` (w/ `GeoCoordinates`, `OpeningHoursSpecification`) |
| `/about/` | `BreadcrumbList`, 2× `Person` |

Not fetched this pass: `services.astro`, `blog/[slug].astro`, `ro/blog/[slug].astro`, `ro/contact.astro` — user-reported inventory for these (Service, FAQPage, BlogPosting, Person, PropertyValue) not independently verified.

## Validation Results

| Schema | Type | Status | Issues |
|---|---|---|---|
| Homepage | `Organization`+`ProfessionalService` | ✅ | Valid, complete: address, telephone, `sameAs` (LinkedIn, TheManifest, RocketReach), stable `@id`. No Google Business Profile in `sameAs` — add if one exists. |
| Homepage | `WebSite` | ✅ | Valid. |
| Homepage | `FAQPage` | ℹ️ | Valid syntax. No SERP rich-result since May 7, 2026 retirement — keep for on-page UX / AI-citation value, don't expect a SERP box. |
| `/ro/` homepage | `Organization`/`WebSite` | ❌ | **Missing entirely.** EN homepage has both; RO homepage only has `FAQPage`. Not "mirrored" as reported — real gap. |
| All pages | hreflang | ❌ | **Zero `<link rel="alternate" hreflang="...">` tags found anywhere.** EN (`/`) and RO (`/ro/`) are structurally parallel but Google has no signal connecting them as language alternates of the same content. |
| `/jobs/` | `JobPosting` (×9) | ❌ | **`datePosted` is identical across all 9 listings and equals today's date (2026-08-14).** Strongly suggests it's generated at request/build time (`new Date()`) rather than each job's real posting date. Google uses `datePosted` for freshness ranking and to decide when a listing looks stale — if every job always shows "posted today," that's either a bug or reads as manipulation. Needs a real, fixed per-job date. |
| `/jobs/` | `JobPosting` (×9) | ⚠️ | `validThrough` missing on all 9 (Google-recommended — without it, Google can't reliably know when to expire stale listings). `baseSalary` missing on all 9 (Google-recommended, increasingly weighted). |
| `/jobs/` | `JobPosting` (4 remote roles) | ⚠️ | `jobLocation.address.addressLocality` set to placeholder strings — `"Full Remote"`, `"Remote (Romania)"`, `"Full Remote (Romania)"` — not real localities, invalid `PostalAddress` usage. `applicantLocationRequirements: Romania` is already correctly set and is the right field for this; the fake locality should be dropped, not fixed with a real value. |
| `/jobs/` | `JobPosting` (2 hybrid/onsite) | ℹ️ | `addressLocality` has extra annotation baked in — `"Timișoara / Giarmata (On-site)"`, `"Bucharest (Hybrid)"`. Locality field should be just the city; work-mode belongs in the description, not jammed into the address. Minor — may affect city-facet matching in Google for Jobs. |
| `/contact/` | `LocalBusiness` | ✅ | Valid, complete — real geo coords, opening hours, address with postal code. |
| `/about/` | `Person` (×2) | ✅ | Valid, present, correct type for founder bios. |

## Root cause priorities

1. **`datePosted` bug** — highest priority. If this is genuinely regenerating on every request/build, every job listing is misrepresenting its actual post date to Google. Fix at the CMS/data layer: `datePosted` must be set once, at actual creation time, and never recomputed.
2. **RO homepage missing Organization/WebSite** — likely a layout include that didn't get ported to the `/ro/` route; check whatever partial/component injects those two blocks on `index.astro` and confirm it's also called from `ro/index.astro`.
3. **No hreflang** — add `<link rel="alternate" hreflang="en" href="https://wise-step.ro/">` / `hreflang="ro"` / `hreflang="x-default"` reciprocally on both homepages (and ideally every paired EN/RO route). This is a site-wide gap, not homepage-only — worth checking Layout.astro for a hreflang partial.

## Recommendations (schema fixes)

See `wise-step-ro-generated-schema.json` for corrected JobPosting shape (remote-role location handling + `validThrough`/`baseSalary` placeholders) and the RO-homepage `Organization`/`WebSite` blocks to add.
