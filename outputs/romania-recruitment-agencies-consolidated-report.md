# Romania IT & Executive Recruitment — Consolidated Competitor Report

Consolidates 4 `/seo-competitor-pages` runs (2026-08-14): Human Rise, Human Direct, Hays Romania, Evolve Today. Each was profiled against its strongest competitive overlap; this report merges all data into one master matrix, one keyword plan, and one prioritized action list, replacing the need to read 4 separate vs-pages.

## Sites profiled + their built comparison

| Site profiled | Model | Compared against | Status |
|---|---|---|---|
| humanrise.ro | Boutique, IT-exclusive, Iași | Brainsource | ✅ Both fetched directly |
| humandirect.eu | Recruiting + HR consulting + staffing, Cluj-Napoca | Brainsource | ⚠️ Own site 403'd — Clutch used as fallback |
| hays.ro | Global specialist recruitment, Bucharest | Manpower Romania | ⚠️ Own site 403'd — search snippets used as fallback |
| evolvetoday.ro | Boutique, IT + exec + HR consulting, Bucharest | Antal International | ✅ Both fetched directly |

## Master feature matrix (all 8 agencies)

| Agency | HQ | Founded/Age | Model | IT Focus | Exec Search | HR Consulting | Staffing/EOR/RPO | Global Network | Pricing Disclosed | Data Reliability |
|---|---|---|---|---|---|---|---|---|---|---|
| **Human Rise** | Iași | Not stated | Boutique, IT-exclusive | ✅ Exclusive | Not stated | Employer branding audits | ❌ | ❌ | ❌ | High — direct fetch |
| **Human Direct** | Cluj-Napoca | 2011 | Recruiting/HR consulting/staffing mix | 40% of business | Not explicit | ✅ 10% | ✅ Permanent+temp | Europe+USA reach | ✅ $5,000+ floor | Medium — Clutch (3rd-party), own site 403'd |
| **Hays Romania** | Bucharest | RO office 2015 | Global specialist recruitment | 1 of 8 verticals | ✅ Retained | ✅ Talent Solutions (RPO/MSP) | Not explicit | ✅ Hays PLC | ❌ | Low-medium — search snippets, own site 403'd |
| **Evolve Today** | Bucharest | ~16 yrs | Boutique, IT+exec+HR consulting | ✅ | ✅ Management/headhunting | ✅ Audit, org diagnosis, career counseling | ❌ | ❌ | ❌ | High — direct fetch |
| **Brainsource** | Cluj-Napoca | Not stated | Network marketplace | ✅ Exclusive | Not stated | ❌ | ✅ 500+ recruiter network | ✅ Ireland/UK/US offices | ❌ ("market-average") | High — direct fetch |
| **Antal International Romania** | Bucharest + 8 offices | 2003 | National/global network | 1 of 8 verticals | ✅ C-level, 30-step process | ✅ Assessment centers, org surveys | ✅ RPO, interim | ✅ 5 continents | ❌ (retained norm) | High — direct fetch (confirmed this session; an earlier attempt at a different Antal URL 404'd) |
| **Manpower Romania** | National | Part of ManpowerGroup | Full-spectrum staffing | 1 of 15+ verticals | ✅ Headhunting | Not explicit | ✅ EOR/PEO/payroll, explicit | ✅ 110+ countries | ❌ | High — direct fetch |
| **EDUROM Recruitment** | Iași | 18 yrs | IT-exclusive technical roles | ✅ Exclusive | Not researched | Not researched | Not researched | ❌ | Not researched | Not researched — name only, from earlier search |

**Read the matrix as:** boutique/local (Human Rise, Evolve Today, EDUROM) vs mid-scale hybrid (Human Direct) vs national/global network (Brainsource, Antal, Hays, Manpower). Pricing is disclosed by exactly one agency in the set — Human Direct, and only via a third-party review platform, not their own site.

## Consolidated keyword strategy

| Pattern | Query | Intent | Owner opportunity |
|---|---|---|---|
| A vs B (branded) | "Human Rise vs Brainsource", "Human Direct vs Brainsource", "Hays vs Manpower Romania", "Evolve Today vs Antal International" | High intent, low volume | One page per pairing (built) |
| Category, national | "best IT recruitment agencies Romania", "top executive search firms Romania" | Medium-high, non-branded | **Not yet built — see recommendation below** |
| Category, local | "agenție recrutare IT Iași", "executive search agency Bucharest", "IT recruitment agency Cluj-Napoca" | Medium | Roundup or city-filtered sections |
| Pricing intent | "IT recruiter Romania cost", "recruitment agency fees Romania" | Medium, uncontested | Human Direct is the only agency with public pricing — first-mover opportunity |
| Service-specific | "EOR Romania", "payroll outsourcing Romania agency" | High, uncontested by boutiques | Manpower-side keyword; none of the 4 boutique/mid sites compete here |
| Alternatives | "Brainsource alternatives", "Antal International alternatives" | Low volume, high conversion | Secondary pages off the primary vs-pages |

## Recommendation: build the roundup hub next

All 4 runs converge on the same 4 competitors (Brainsource, Antal, Manpower, plus EDUROM unresearched). Per the skill's internal-linking guidance, the efficient next asset is a single:

**"Best IT & Executive Recruitment Agencies in Romania (2026)"** roundup — `ItemList` schema, one page, sections for boutique/local vs national/global, each of the 8 agencies above gets one card, and every existing vs-page cross-links into it instead of only linking pairwise. This replaces the need for further 1:1 pages (e.g. "Evolve Today vs Human Direct") — a roundup captures the differentiation with less duplicated content and higher-volume non-branded keywords.

### Minimal ItemList schema for the roundup (ready to drop in)

```json
{
  "@context": "https://schema.org",
  "@type": "ItemList",
  "name": "Best IT & Executive Recruitment Agencies in Romania (2026)",
  "itemListOrder": "https://schema.org/ItemListUnordered",
  "numberOfItems": 7,
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Human Rise", "url": "https://humanrise.ro" },
    { "@type": "ListItem", "position": 2, "name": "Human Direct", "url": "https://humandirect.eu" },
    { "@type": "ListItem", "position": 3, "name": "Hays Romania", "url": "https://www.hays.ro" },
    { "@type": "ListItem", "position": 4, "name": "Evolve Today", "url": "https://evolvetoday.ro" },
    { "@type": "ListItem", "position": 5, "name": "Brainsource", "url": "https://brainsource.io" },
    { "@type": "ListItem", "position": 6, "name": "Antal International Romania", "url": "https://www.antal.com/recruitment/romania-bucharest-v" },
    { "@type": "ListItem", "position": 7, "name": "Manpower Romania", "url": "https://manpowerromania.com" }
  ]
}
```

(EDUROM omitted — not yet independently fetched/verified; add only after direct research.)

## Data quality log (session-wide)

| URL | Result | Handling |
|---|---|---|
| humanrise.ro | ✅ Direct fetch | — |
| brainsource.io | ✅ Direct fetch | — |
| humandirect.eu / www.humandirect.eu | ❌ 403 both | Fell back to Clutch.co (3rd-party, still cited) |
| hays.ro | ❌ 403 | Fell back to Google search snippets of hays.ro/en subpages (weakest source in the set — flag before publishing anything using it) |
| evolvetoday.ro | ✅ Direct fetch | — |
| antal.com/recruitment/romania-Iasi-sme | ❌ 404 | Superseded — later fetched antal.com/recruitment/romania-bucharest-v successfully |
| antal.com/recruitment/romania-bucharest-v | ✅ Direct fetch | Used as final Antal source |
| manpowerromania.com | ✅ Direct fetch | — |
| Michael Page Romania (searched, not fetched — no dedicated URL found) | ❌ No verifiable Romania-specific data | Excluded from all comparisons, not fabricated |

**Before publishing anything that cites Hays or Human Direct data:** re-attempt a direct/rendered fetch of hays.ro and humandirect.eu — both are currently sourced secondhand.

## Prioritized next steps

1. Build the roundup hub (above) — highest leverage, converts 4 isolated vs-pages into one cross-linked cluster targeting non-branded, higher-volume queries.
2. Re-verify hays.ro and humandirect.eu directly before any of their comparison pages go live — both currently rest on third-party/snippet data.
3. Research EDUROM Recruitment directly (18-yr Iași IT specialist) — only named competitor in the landscape with zero verified data; likely candidate for a fifth vs-page or a roundup entry once fetched.
4. Build "Evolve Today vs Human Direct" only if the roundup doesn't cover the recruiting+HR-consulting+staffing niche clearly enough — otherwise skip, roundup supersedes it.
5. Publish the pricing-intent page (Human Direct's $5K+ floor) — uncontested keyword cluster identified in the humandirect.eu run, still open.

## Source files (unchanged, this report supersedes them for reading — originals kept for the full page templates)

- `humanrise-ro-comparison-page-vs-brainsource.md` / `humanrise-ro-comparison-schema.json` / `humanrise-ro-competitor-pages-strategy.md`
- `humandirect-eu-comparison-page-vs-brainsource.md` / `humandirect-eu-comparison-schema.json` / `humandirect-eu-competitor-pages-strategy.md`
- `hays-ro-comparison-page-vs-manpower.md` / `hays-ro-comparison-schema.json` / `hays-ro-competitor-pages-strategy.md`
- `evolvetoday-ro-comparison-page-vs-antal.md` / `evolvetoday-ro-comparison-schema.json` / `evolvetoday-ro-competitor-pages-strategy.md`
