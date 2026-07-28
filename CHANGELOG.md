# Changelog

All notable changes to this dataset are recorded here, including
demotions — a match that no longer appears is documented, not silently
dropped.

## [1.0.1] — 2026-07-28

County metadata completed for two multi-county matches after a
systematic audit. No match identities changed.

- A 2026-07-28 audit cross-checked every published multi-WDID match's
  `county` field against DWR's own per-structure county (the ground
  truth in DWR's structures data) and found two rows, both originally
  promoted via hand-verified batch 3, where `county` listed only one of
  the several counties their matched WDIDs actually span:
  - **Bijou Irrigation Company** (entity_id 19871029704): `county` now
    `WELD;MORGAN;ARAPAHOE` (was `WELD` only).
  - **Huerfano-Cucharas Irrigation Company** (entity_id 19871109488):
    `county` now `PUEBLO;HUERFANO` (was `PUEBLO` only).
- No `entity_id`, `wdids`, `water_source`, `earliest_year`,
  `matched_on`, or `citation_url` values changed for either row — this
  release corrects `county` completeness only.
- Still **300 tier-1 verified company-to-WDID matches**; the correction
  changes two cells, not the match count.

## [1.0.0] — 2026-07-27

Initial public release: **300 tier-1 verified company-to-WDID matches**
for Colorado mutual ditch and reservoir companies, each with a citation
to the underlying Colorado DWR record.

- Seeded from the Open Water Foundation's
  `owf-data-co-ditch-and-reservoir-companies` dataset, reconciled
  against Colorado Secretary of State business-entity records for
  company identity.
- Matches published only where DWR's own records assert the
  company-to-structure relationship beyond doubt — see the tier-1
  standard at [getditchbook.com/methods/](https://getditchbook.com/methods/).
- Three matches published in earlier, non-public staging of this
  dataset were demoted on 2026-07-21 after a basin-conflict audit found
  they didn't hold up. They are excluded from this release; the
  demotion is recorded here rather than disappearing without a trace.
- A fourth match — Park Ditch Company (entity_id 19891032074, WDID
  3800925) — was a wrong-company match found in pre-release review on
  2026-07-27 and withdrawn before this dataset was ever published: the
  DWR match fit the distinct company Park Ditch And Reservoir Company
  (Carbondale, Garfield County), not Park Ditch Company (Pagosa
  Springs, Archuleta County). There was no live claim to retract —
  recorded here anyway, on the same transparency principle as the
  three above.
- `suppression-list.csv` is included in this release: the public
  record of those four withdrawn matches (company, structure, date,
  reason). Rows are never removed from it — see `README.md` §
  "Suppressed matches" for why.
- `changes-keyed.csv` is included: the cell-level manifest (660 rows)
  of the same matches as contributed back to the OWF seed dataset via
  pull request, keyed for independent application or audit.
