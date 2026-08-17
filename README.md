# DitchBook — Colorado ditch company to WDID matches (tier-1)

> **STATUS: PUBLIC since 2026-07-27** at
> github.com/ndavipt/ditchbook-open-data (decided on the 2026-07-27 OWF
> call: standalone public repository, plus a separate CSV contribution
> into OWF's dataset via PR). License below is FINAL (CC BY 4.0,
> confirmed at publication). This directory is the repo-side source of
> the published package — keep it, the GitHub repo, and
> `water/matches-published.csv` hash-identical on every change.

## Overview

Verified matches between Colorado mutual ditch and reservoir companies
(as registered with the Colorado Secretary of State) and their water
structures (WDIDs) in Colorado DWR records — the organization-to-WDID
relationship that public state datasets stopped exposing directly.
**643 companies** are matched at tier-1: published only where state
records agree beyond doubt, with a citation URL to the underlying DWR
record on every row. Ambiguous candidates are excluded, not guessed.

The matches power the free public registry at
[getditchbook.com](https://getditchbook.com/) — every row's company has
a public profile page, and the full pipeline is documented at
[getditchbook.com/methods/](https://getditchbook.com/methods/).

## Data dictionary

`ditchbook-company-wdid-matches.csv`, one row per matched company:

| Column | Meaning |
|---|---|
| `entity_id` | Colorado Secretary of State business-entity ID for the company. Blank on a handful of rows where the SoS record link is still being reconciled; such rows were matched by exact normalized company name (unique across the census) instead. |
| `company_name` | Company name as registered with the Colorado SoS. |
| `wdids` | The company's matched DWR structure ID(s); multiple WDIDs separated by `;`. |
| `water_source` | Water source of the earliest decreed right, as recorded by DWR. |
| `earliest_year` | Year of the company's earliest decreed (absolute) water right per DWR net-amounts records. |
| `county` | County of the matched structure, per DWR. |
| `matched_on` | Internal provenance label: either the normalized name key the match was made on, or a verification-batch tag (e.g. `batch2-promoted-verified`). Heterogeneous by history; kept for transparency rather than cleaned away. |
| `citation_url` | Link to the DWR record supporting the match — the receipt. |

## Workflow (summary — full documentation on the methods page)

1. Census seeded from the [OWF Colorado ditch and reservoir companies
   dataset](https://github.com/OpenWaterFoundation/owf-data-co-ditch-and-reservoir-companies),
   reconciled against Colorado SoS business-entity data (1,387 companies as
   of 2026-08-03, refreshed monthly).
2. Companies matched to DWR CDSS structures by entity identity or
   unique exact normalized name, with basin-consistency checks.
3. Tier-1 bar: published only where records agree beyond doubt; every
   row carries its citation. Post-publication conflicts demote the row
   to review (three matches were demoted 2026-07-21, a fourth withdrawn
   2026-07-27 in pre-release review — demotions are part of the
   record).

## Update cadence

The registry refreshes monthly against SoS data; matches grow as
verification clears the backlog. Published versions of this dataset are
dated; material changes (additions, demotions) are noted in the
changelog below.

## Attributions

- Seed list: Open Water Foundation,
  `owf-data-co-ditch-and-reservoir-companies` — the open data this
  project grew from, gratefully credited.
- Company registrations and standings: Colorado Secretary of State
  business-entity data.
- Water rights and structures: Colorado DWR / CDSS public records.
- DARCA membership context: Ditch and Reservoir Company Alliance.

## Disclaimer

This is a compilation of public records, offered in good faith with a
citation on every row so any claim can be checked at the source.
DitchBook is not affiliated with any listed company, the State of
Colorado, or DARCA. No warranty; verify against the cited state record
before relying on a row for any consequential purpose. Errors reported
to the maintainer are corrected same-day.

## Maintainers

Nick Davis — DitchBook, Loveland, Colorado.
nick@getditchbook.com · (970) 460-6532

## License

Intended license: **Creative Commons Attribution 4.0 (CC BY 4.0)** —
use, share, adapt, including commercially, with attribution to
"DitchBook (getditchbook.com)". The matches are DitchBook's
verification work product over public state records; the underlying
state records are public data. Final license to be confirmed in
coordination with the Open Water Foundation (whose own dataset license
is likewise being determined — alignment is on the 2026-07-27 agenda).

## How to cite

DOI (all versions, resolves to latest): https://doi.org/10.5281/zenodo.21711149
(minted 2026-07-30 via Zenodo's GitHub integration; badge + CITATION.cff
live on the public repo)

> DitchBook, "Colorado ditch company to WDID matches (tier-1)",
> getditchbook.com/methods/, data as of 2026-08-17.

## Versioning

This is **v1.16.0**, published 2026-08-17. See "Changelog," below, for
release history; demotions and corrections are recorded there, not
silently dropped.

## Changelog

- **2026-08-17 (v1.16.0) — 643 tier-1 matches / 1,037 distinct WDIDs**:
  Five long-running HOLD cases closed in promotion batch 69 after DitchBook's
  CDSS Imaged Documents importer inventoried 4,092 official attachments and
  reviewed 90 bounded pages. Thompson Rivers Storage And Irrigation Company,
  LLC is associated with Bacon Reservoir (`0403307`), and Porter Ditch And
  Reservoir Company with Porter Ditch (`4500725`). Excelsior Irrigating
  Company, Farmers Irrigating Ditch & Reservoir Company, and No. 10 Ditch
  Company are published only as explicitly scoped historical, predecessor, or
  contract-right associations beside the retained current/predecessor company.
  The complete 68-stage pipeline reproduces the 643-row publication table
  byte-for-byte.

- **2026-08-17 (v1.15.0) — 638 tier-1 matches / 1,035 distinct WDIDs**:
  197 verified company associations and 235 distinct WDIDs added since
  v1.9.0 through the subsequent primary-record, court-record, map, title,
  operator, and targeted closure batches. The release includes the first
  deterministic CDSS Imaged Documents evidence pass: a DWR-attached 1930
  CA1248 hearing establishes the 1911 Los Pinos Ditch Company as the historic
  claimant for WDID `3100512`. The 1959 Los Pinos Irrigating Ditch Company
  remains the current listing; the historical association does not assert
  current ownership or operation. The complete 66-stage pipeline reproduces
  the 638-row publication table byte-for-byte.

- **2026-08-12 (v1.9.0) — 441 tier-1 matches / 800 distinct WDIDs**:
  Six matches added in promotion batch 19 using original formation records,
  DWR contacts and right schedules, and Colorado water-court or State Engineer
  corroboration. Added Alamo Ditch Company; Allen Mesa Ditch and Reservoir
  Company; Baca Irrigating Ditch Company; Midland Ditch Company; The Meadow
  Island Ditch Company No. Two (2); and The Mutual Hyde Ditch Company. Mutual
  Hyde contributes Ideal Ditch, Hyde Ditch, and Hyde's adjudicated alternate
  point. The complete 21-step pipeline reproduces the 441-row publication
  table byte-for-byte with no new unsanctioned WDID collision.

- **2026-08-12 (v1.8.0) — 435 tier-1 matches / 792 distinct WDIDs**:
  48 matches added across promotion batches 11–18. These batches extend the
  evidence channels beyond automated contact-name matching to direct DWR
  contacts, original formation filings, recorded-title and operator records,
  court priorities, exact legal descriptions, and map topology used only as
  geographic corroboration. Batch 18 adds New Brantner Extension Ditch
  Company; Mogote Northeastern Consolidated Ditch Company (two WDIDs);
  Sanborn Reservoir and Ditch Company; Talmadge And Gibson Ditch And
  Reservoir Company; White Ditch No. 2, Incorporated; White Ditch No. 3,
  Incorporated; and Trickle Ditch Company. The complete 20-step pipeline
  reproduces the 435-row publication table byte-for-byte.

- **2026-07-21** — initial staged package: 301 tier-1 matches; three
  previously published matches demoted after basin-conflict audit
  (demotions are recorded here deliberately).
- **2026-07-27** — 300 tier-1 matches: a fourth match, Park Ditch
  Company (entity_id 19891032074, WDID 3800925), was found to name the
  wrong company in pre-release review and withdrawn before this
  package was ever published — see `CHANGELOG.md` in the staged
  package for the full note.
- **2026-07-28 (county metadata)** — county metadata completed for two
  multi-county matches, both originally promoted via hand-verified
  batch 3: Bijou Irrigation Company (entity_id 19871029704) now lists
  `WELD;MORGAN;ARAPAHOE` (was `WELD` only) and Huerfano-Cucharas
  Irrigation Company (entity_id 19871109488) now lists
  `PUEBLO;HUERFANO` (was `PUEBLO` only). A systematic audit cross-checked
  every multi-WDID promoted match's published county field against
  DWR's own per-structure county and found these two rows' county field
  covered only one of the several counties their matched WDIDs actually
  span. No match identities, WDIDs, water sources, or years changed —
  county metadata only.
- **2026-07-28 (v1.1.0) — 315 tier-1 matches**: 15 matches added via
  promotion batch 4, each independently researched and verified across
  three review passes before promotion. Includes DitchBook's first
  sanctioned joint listing — Little Ditch 1, LLC and Little Ditch 2,
  LLC, entity_ids 20221692052 and 20221692098, both published sharing
  the identical 4-WDID structure set (3815165, 3815166, 3815169,
  3815192) because Colorado DWR's own record names both companies as
  distinct joint contacts on those structures and both identities are
  independently SoS-corroborated — not a data error, a deliberate
  dual-ownership record. One further candidate from the same batch
  (Lake Canal Company, a blank-entity_id census row) was reviewed and
  rejected — its associatedContacts match collides with the
  already-published Lake Canal Reservoir Company aggregate and does not
  hold up under review — and is not published; the rejection is
  recorded in DitchBook's internal audit trail, not silently dropped.
- **2026-08-04 (v1.2.0) — 327 tier-1 matches**: 12 matches added via
  promotion batch 5 (three-pass adversarial review: evidence assembly,
  independent re-derivation, reconciliation — see
  `water/audits/2026-08-04-match-audits.md` in the DitchBook repo).
  Added (all `matched_on=batch5-promoted-verified`): Big Ditch Company,
  Box Springs Canal And Reservoir Company, Catlin Canal Company,
  Colorado Canal Company, Home Supply Ditch Company Inc., Lake
  Arrowhead Water Association, Last Chance Ditch Company, Saddle
  Mountain Mutual Water Company, The Fort Lyon Canal Company, The
  United Water Company, The Water Supply And Storage Company, The
  Welton Land and Water Company — 51 WDIDs total. Several of these
  publish only a hand-verified subset of a larger multi-county WDID
  footprint (e.g. Catlin Canal Company withholds a Division-4 Saguache
  structure pending decree research; Box Springs Canal And Reservoir
  Company withholds an inactive Teller-County pair) — the withheld
  WDIDs are not silently absent; see the audit for what was held back
  and why. One candidate from the same batch (Farmers Reservoir And
  Irrigation Company, "FRICO") was escalated rather than promoted, and
  one (Farmers Water Development Corporation's possible tie to the
  Naturita structure, WDID `6000707`) is recorded as UNDECIDABLE
  pending further decree research — neither is published. No previously
  published match changed identity, WDID, water source, earliest year,
  or county as part of this release.
- **2026-08-05 (v1.2.1) — 326 tier-1 matches**: one match withdrawn.
  Palisade Irrigation District (published with a blank `entity_id`;
  WDID 7200817, Colorado River, Mesa County) was removed from the
  census as part of a project-wide correction: an irrigation district
  is a statutory taxing/assessment authority, not a shareholder-owned
  mutual ditch company, and the census's own admission rules exclude
  them (see `specs/census-triage-protocol.md` "Admission rules," A3,
  in the DitchBook repo). Two further Title 37 districts were removed
  from the census at the same time (Riverside Irrigation District,
  Orchard Mesa Irrigation District) but carried no published match, so
  this is the only row this release affects. No other match's
  identity, WDID, water source, earliest year, or county changed as
  part of this release.
- **2026-08-05 (v1.3.0) — 351 tier-1 matches**: 25 matches added via
  promotion batch 6 (three-pass adversarial review plus a fourth upgrades
  mini-review — see `water/audits/2026-08-05-match-audits.md` in the
  DitchBook repo), drawn from a new evidence class: Colorado Dam Safety's
  owner-of-record field, cross-checked against DWR structure records
  rather than trusted alone. Added (all `matched_on=batch6-promoted-verified`):
  Blue Lake Reservoir Company, Boulder And White Rock Ditch And Reservoir
  Company, Cedar Mesa Reservoir Company, Denver-View Reservoir And
  Irrigation Company, Eastdale Mutual Ditch And Reservoir Company, Farmers
  Reservoir And Irrigation Company, Granby Ditch And Reservoir Company,
  Grand Mesa Reservoir Company, Kern Reservoir And Ditch Company, Leon
  Park Reservoir Company, Leroux Creek Water Users' Association, Loveland
  Lake and Ditch Company, Marcot Park Ditch And Reservoir Company, Needle
  Creek Reservoir Association, Paradox Valley Canal & Reservoir Co.,
  Sanchez Ditch And Reservoir Company, Seven Lakes Reservoir Company, St.
  Vrain Reservoir And Fish Company, Surface Creek Ditch And Reservoir
  Company, Terror Ditch And Reservoir Company, The Tunnel Water Company,
  Trinchera Irrigation Company, Twin Lakes Reservoir And Canal Company,
  Weir And Johnson Ditch And Reservoir Company, West Reservoir And Ditch
  Company — 67 WDIDs total. Two matches held in earlier releases were
  resolved and promoted on new primary-document evidence: St. Vrain
  Reservoir And Fish Company (water-court decrees CA4790 and 02CW0334) and
  Surface Creek Ditch And Reservoir Company (a Secretary of State
  filing-history resolution to the 1886 entity, entity_id 19871097603,
  over a same-name, dormant-since-2016 2014 shell at the same address).
  Farmers Reservoir And Irrigation Company ("FRICO"), recorded UNDECIDABLE
  in v1.2.0, was resolved and promoted on 5 WDIDs — its own filed Articles
  of Amendment name three of the five structures as its own corporate
  divisions. Grand Mesa Reservoir Company publishes 3 of 4 dam-cited
  WDIDs; the fourth is withheld pending independent attribution beyond the
  dam owner field alone. **One further match adjudicated PROMOTE by the
  same review is deliberately not in this release**: The Farmers Water
  Development Company (WDID 6003507) is evidentially sound but held back
  for a pipeline-mechanics reason, not an evidentiary one — merging it
  collides with the already-published Naturita Canal And Reservoir
  Company's WDID 6000707 inside the reproducibility pipeline (a chain-order
  defect requiring a reviewed code change before it can ship safely). It
  is not suppressed and not refuted; see
  `water/audits/2026-08-05-match-audits.md` sec 11.3 for the full record,
  including the drafted-but-unapplied correction that will accompany its
  eventual release. Consistent with this dataset's publish-only-what-
  reproduces discipline: a match is not published until it survives the
  full reproducibility chain, not merely adjudication.
- **2026-08-05 (v1.4.0) — 367 tier-1 matches**: two releases in one version
  bump.

  *+15 via promotion batch 7* (351 → 366): the sec 9.1 normalizer-gap
  cohort itself — every company DWR's own records name only via an
  abbreviation (`RES`→RESERVOIR, `DTCH`→DITCH, etc.) or a dropped trailing
  noun that the live tier-1 matcher cannot reach on its own, adjudicated
  across three review passes plus a recovered pass-2 document (see
  `water/audits/2026-08-05-batch7-final.md` in the DitchBook repo). Added
  (all `matched_on=batch7-promoted-verified`): Uncompahgre Valley Water
  Users Association, The San Luis Valley Canal Company, Manassa Land And
  Irrigation Company, Fruitland Irrigation Company, Greeley Irrigation
  Company, Upper Platte and Beaver Canal Company, The Lower Platte and
  Beaver Canal Company, Sherwood Irrigation Company, Warren Lake Reservoir
  Company, Schneider Ditch Company, Farmers Pawnee Canal Company, Park
  Reservoir Company, Grant Reservoir Company, Taylor & Gill Ditch Company,
  Beaver Creek Ditch Company — 42 WDIDs total. Debut of a new corroborating
  signal, DWR's own structure-level company-code AKA field, used only to
  corroborate an owner-name match, never alone as a citation. Measured
  before the merge, for the first time correctly predicted in advance from
  the evidence class itself: 0 of the 15 reachable by the live matcher on
  its own (every row was reached by a transform the matcher cannot
  perform), so nothing needed a hand-verified rescue subset — the whole
  batch replayed as filed.

  *+1, The Farmers Water Development Company* (366 → 367): closes the
  batch-6 deferral first recorded in this changelog's v1.3.0 entry. A
  pipeline-mechanics fix shipped in the DitchBook repo (`water/audits/2026-08-05-pipeline-fix-design.md`,
  "corrections constrain at birth") that enforces the corrections ledger
  the moment a corrected company's row re-enters the published set, not
  only at the end of the pipeline — closing the exact chain-order collision
  that blocked the earlier merge. WDID `6003507` now publishes for FWD;
  Naturita Canal And Reservoir Company's WDID `6000707` is untouched
  throughout. The fix constrains FWD to the single WDID this batch actually
  verified; it asserts nothing about who owns `6000707`.
- **2026-08-08 (v1.5.0) — 374 tier-1 matches**: 7 matches added via
  promotion batch 8 (+7 WDIDs, all single-WDID promotions), drawn from
  two independently-sourced adjudication tracks — fresh discovery via
  a structure-name-exact channel, plus evidence-closure on carryovers
  from batches 6 and 7 — cross-examined by a third, adversarial review
  pass before promotion (see `water/audits/2026-08-08-match-batch8.md`
  in the DitchBook repo). Added (all `matched_on=batch8-promoted-verified`):
  Beaver Farmers Canal And Ditch Company, Dave Miller Mutual Ditch
  Company, Dixon Canon Ditch And Reservoir Company, Hermosa Company
  Ditch, Mitchell-Cooper Ditch And Pipeline Company, High Line Canal
  Company, Mayham Reservoir Corporation. Each match rests on a
  statewide-unique structure name plus independent corroboration
  (SoS-address-to-structure geographic concordance, an
  appropriation-to-incorporation date chain, or a DWR AKA
  company-code decode). One track-level match (Sunny Slope Reservoir
  Company) was declined on evidence-custody grounds rather than
  promoted. No previously published match changed identity, WDID,
  water source, earliest year, or county as part of this release.
- **2026-08-09 (v1.6.0) — 376 tier-1 matches**: 2 matches added via
  promotion batch 9: Gunnison and Ohio Creek Canal Company (`5900569`)
  and Richfield Canal Company (`2200616`). Both combine a
  statewide-unique company/structure name with a tight
  appropriation-to-incorporation date chain. The batch also debuted the
  refutations-ledger gate in the scoring pipeline so previously adjudicated
  candidates cannot silently cycle back into a later queue. No existing
  published attribution changed.
- **2026-08-11 (v1.7.0) — 387 tier-1 matches / 742 distinct WDIDs**:
  11 matches added via promotion batch 10 after a fixed 20-company evidence-
  closure review. Added (all `matched_on=batch10-promoted-verified`): The
  Crystal Spring, Ditch and Pipeline Corp.; Divide Canal and Reservoir
  Company; Wellman Ditch Company; Andrews-Farwell Ditch and Reservoir
  Company; Tetsel Mutual Ditch Company; The Carr and Tyler Ditch and
  Reservoir Company; Rio Grande and San Luis Irrigation Company; Leon Lake
  Ditch and Reservoir Company; Anaconda Ditch Co., Incorporated; Sellers &
  McClane Reservoir & Ditch Company; and The J. & M. Hughes Ditch Company.
  Thirteen company-to-WDID links were added but only 12 new distinct WDIDs:
  `7203839` is deliberately shared by Leon Lake and the already-published
  Grand Mesa Water Users Association because DWR names both as contacts.
  The earlier Grand Mesa attribution was retained, not overwritten, and the
  joint listing is recorded in the project's hard-enforced ledger. Two
  rejected candidates (La Garita Reservoir Company and Storm Ditch Company,
  covering 7 proposed WDIDs) were added to the refutations gate; 7 further
  candidates remain open without publication. The full pipeline reproduces
  the 387-row table byte-for-byte.
