# Changelog

All notable changes to this dataset are recorded here, including
demotions — a match that no longer appears is documented, not silently
dropped.

## [1.1.0] — 2026-07-28

15 matches added via promotion batch 4 (three independent review passes
per candidate: researcher, adversarial verifier, and Nick's product
decision on the one candidate that needed it). 1 candidate rejected in
review — recorded in the audit trail, not published. Now **315 tier-1
verified company-to-WDID matches**.

- Added (all `matched_on=batch4-promoted-verified`): Arkansas
  Groundwater and Reservoir Association, Bear River Reservoir Co.,
  Beaver Reservoir Company, Big Creek Reservoir Company, Consolidated
  Reservoir Inc., Four Mile Ditch Association, Gardner Park Mutual
  Reservoir Company, Little Ditch 1 LLC, Little Ditch 2 LLC, Otero
  Ditch Co., Salvation Ditch Company, The Pine River Canal Company, The
  Pleasant Valley and Lake Canal Company, The Ward Canal Company,
  Williams Canal Company.
- **First sanctioned joint listing:** Little Ditch 1, LLC (entity_id
  20221692052) and Little Ditch 2, LLC (entity_id 20221692098) are both
  published, sharing the identical 4-WDID structure set (3815165,
  3815166, 3815169, 3815192; Upper Irrigation Pond, Middle Irrigation
  Pond, Leland Wetland Pond, Parcel 2 Irrigation Pond, Pitkin County).
  Colorado DWR's own associatedContacts record lists both companies as
  distinct, deliberate, numbered co-contacts on all 4 structures — not
  a lookalike-name collision like the earlier Lake Canal case, where
  only one candidate was the real owner. Both entities are Good
  Standing Colorado LLCs formed the same day (2022-07-19) by the same
  sponsor via the same registered agent. Policy: when DWR's own record
  names two companies jointly on identical structures and both
  identities are independently SoS-corroborated, both are published,
  sharing the WDIDs — see `getditchbook.com/methods/` for the general
  tier-1 standard this dataset publishes under.
- **Rejected, not published:** Lake Canal Company (a blank-entity_id
  census row) was reviewed and rejected. Its raw DWR contact string
  includes a bare "LAKE CANAL" entry that collides, after name
  normalization, with "Lake Canal Company" — but the definitive
  company-level contact for those structures is "LAKE CANAL RESERVOIR
  CO," a distinct, already-published company (Lake Canal Reservoir
  Company, entity_id 19871003984). Independent re-confirmation of a
  correction already on file from 2026-07-11. No live claim was ever
  published for Lake Canal Company; there is nothing to retract, only
  a candidate that did not clear review — recorded here on the same
  transparency principle as the withdrawn matches above.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- **2026-07-28 addendum (still 1.1.0, unpublished at the time):** 2
  matches re-keyed from name (blank `entity_id`) to `entity_id` after
  the blank-`BusinessEntity_ID` census row each had anchored was merged
  as a duplicate of an already-registered company: Consolidated Home
  Supply Ditch -> Consolidated Home Supply Ditch And Reservoir Company
  (entity_id 19871004185, WDID 0404136) and Bull Creek Reservoir
  Company -> Bull Creek Reservoir Canal & Power Company (entity_id
  19871034325, WDIDs incl. 7200718). Neither row's `wdids`,
  `water_source`, `earliest_year`, `county`, or `matched_on` value
  changed, and the total match count is still **315** — see
  `water/corrections.csv` in the DitchBook repo for the full rationale.

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
