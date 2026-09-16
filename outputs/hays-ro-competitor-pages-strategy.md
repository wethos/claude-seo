# Competitor Pages Strategy — hays.ro

Analyzed 2026-08-14. Hays Romania = specialist professional recruitment, part of Hays PLC (global, London-listed), Bucharest office since 2015, 8 industry specialisms, 12-week placement guarantee, Talent Solutions (RPO/MSP).

## Fetch issue — action needed

`hays.ro` returned **HTTP 403 Forbidden** on direct WebFetch. All Hays data sourced from Google-indexed search snippets of hays.ro/en subpages, not a live-rendered page. **Before publishing:** re-verify specialisms list, guarantee terms, and Talent Solutions description against the live site (headless render or manual paste) — snippet data can be stale relative to current site copy.

## Competitor landscape found

| Competitor | Type | Overlap w/ Hays | Page opportunity |
|---|---|---|---|
| [Manpower Romania](https://manpowerromania.com) | Global multinational (110+ countries), full-spectrum staffing + EOR/PEO/payroll | High — same global-brand tier, different model (specialist vs full-spectrum) | ✅ Built: `hays-ro-comparison-page-vs-manpower.md` |
| Antal International Romania | Global brand, IT/engineering/HR, retained + contingent tiers | Medium-high — global brand overlap, smaller scale than Hays | Recommended next: "Hays vs Antal International" |
| Michael Page Romania | Global professional recruitment brand | Unknown — searched, found **no verifiable Romania-specific data** this run (search returned unrelated Bucharest agencies) | Do not build until Michael Page's actual Romania presence is confirmed to exist and is independently verifiable |
| Adecco / Randstad Romania | Global staffing multinationals | Not researched this run | Candidate for roundup or future vs-page |

## Primary deliverable (built this run)

**Hays vs Manpower Romania** — `hays-ro-comparison-page-vs-manpower.md` + `hays-ro-comparison-schema.json`. Chosen because Manpower Romania had a directly fetchable site with strong published detail (named enterprise clients, explicit EOR/PEO/payroll offering), giving the most verifiable pairing available despite Hays's own fetch failure.

## Keyword targeting

| Pattern | Query | Intent signal |
|---|---|---|
| A vs B | "Hays vs Manpower Romania" | Low volume, high intent (branded) |
| Category roundup | "global recruitment agencies Romania" | Medium — non-branded |
| Category roundup | "agenții de recrutare multinaționale România" | Medium |
| Use-case split | "specialist recruitment vs staffing agency Romania" | Medium — maps directly to the Hays/Manpower model split |
| EOR-specific | "EOR Romania" / "payroll outsourcing Romania agency" | High — Manpower-side keyword Hays doesn't compete on |

### Title tag formulas
- Vs page: `Hays vs Manpower Romania: Specialist Recruitment or Full-Spectrum Staffing? (2026)`
- Roundup: `Top Global Recruitment Agencies Operating in Romania (2026 Guide)`

## Content gap / opportunity

Manpower is the only one of the two with an explicit EOR/PEO/payroll-outsourcing offering and named enterprise clients (Ericsson, DHL, Oracle, Shell, Siemens) publicly stated — a page targeting "EOR Romania" or "payroll outsourcing Romania" keyword cluster would favor Manpower's positioning and is currently uncontested by Hays's public copy.

## Next steps (not yet built)

1. Re-verify hays.ro content directly (403 blocked this run) before publishing the built comparison page.
2. Build "Hays vs Antal International Romania" — both global brands, Antal data already partially verified from the humanrise.ro run (flagged there as search-snippet sourced, same caveat applies).
3. Confirm whether Michael Page operates independently in Romania before attempting that pairing — this run found no independently verifiable Romania-specific data.

## Error log
- `hays.ro` → 403 (direct fetch); fell back to search snippets of hays.ro/en subpages.
- Michael Page Romania search → no relevant results, only unrelated Bucharest boutique agencies surfaced.
