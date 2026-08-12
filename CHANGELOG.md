# Changelog

All notable changes to this dataset are recorded here, including
demotions — a match that no longer appears is documented, not silently
dropped.

## [1.9.0] — 2026-08-12

Six companies added in promotion batch 19, covering eight new distinct WDIDs.
Now **441 tier-1 verified company-to-WDID matches / 800 distinct WDIDs**.

- Added Alamo Ditch Company; Allen Mesa Ditch and Reservoir Company; Baca
  Irrigating Ditch Company; Midland Ditch Company; The Meadow Island Ditch
  Company No. Two (2); and The Mutual Hyde Ditch Company.
- Mutual Hyde contributes a verified three-point operated system: Ideal Ditch,
  Hyde Ditch, and Hyde's adjudicated alternate point of diversion.
- Evidence combines original formation/acquisition records with DWR contacts,
  legal locations and right schedules, plus Colorado water-court or State
  Engineer corroboration where available. Map labels were used only to verify
  geography, never to create ownership.
- Four additional researched companies were withheld: two carrier-canal
  laterals with no independent WDID, one government-project transfer missing
  its structure schedule, and one acquired Rio Grande system whose legal point
  could not yet be recovered.
- The complete 21-step DitchBook pipeline reproduces the 441-row table
  byte-for-byte, with no new unsanctioned WDID collision.

## [1.8.0] — 2026-08-12

48 companies added across promotion batches 11–18, covering 50 new distinct
WDIDs. Now **435 tier-1 verified company-to-WDID matches / 792 distinct
WDIDs**.

- Expanded evidence channels include direct DWR contacts, original formation
  filings, recorded-title and operator records, court priorities, exact legal
  descriptions, and map topology used only as geographic corroboration.
- Batch 18 adds New Brantner Extension Ditch Company; Mogote Northeastern
  Consolidated Ditch Company (two WDIDs); Sanborn Reservoir and Ditch Company;
  Talmadge And Gibson Ditch And Reservoir Company; White Ditch No. 2,
  Incorporated; White Ditch No. 3, Incorporated; and Trickle Ditch Company.
- The complete 20-step DitchBook pipeline reproduces the 435-row table
  byte-for-byte, with no new unsanctioned WDID collision.

## [1.7.0] — 2026-08-11

11 companies added via promotion batch 10 after a fixed 20-company
evidence-closure review. Thirteen company-to-WDID links were added, covering
12 new distinct WDIDs. Now **387 tier-1 verified company-to-WDID matches / 742
distinct WDIDs**.

- Added (all `matched_on=batch10-promoted-verified`): The Crystal Spring,
  Ditch and Pipeline Corp.; Divide Canal and Reservoir Company; Wellman Ditch
  Company; Andrews-Farwell Ditch and Reservoir Company; Tetsel Mutual Ditch
  Company; The Carr and Tyler Ditch and Reservoir Company; Rio Grande and San
  Luis Irrigation Company; Leon Lake Ditch and Reservoir Company; Anaconda
  Ditch Co., Incorporated; Sellers & McClane Reservoir & Ditch Company; and
  The J. & M. Hughes Ditch Company.
- **Second sanctioned joint listing:** WDID `7203839` is shared by Leon Lake
  Ditch and Reservoir Company and the already-published Grand Mesa Water
  Users Association because DWR names both as distinct contacts. The Grand
  Mesa attribution was retained, not overwritten.
- Two candidates were rejected rather than stretched to publication: La
  Garita Reservoir Company (5 proposed WDIDs) and Storm Ditch Company (2).
  Seven further candidates remain open without publication.
- The complete 12-step pipeline reproduces the 387-row table byte-for-byte,
  with zero unsanctioned WDID conflicts.
- Full adjudication record is in
  `water/audits/2026-08-11-match-batch10.md` in the DitchBook repo.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.

## [1.6.0] — 2026-08-09

2 companies added via promotion batch 9 — the scoring pipeline's
hardened-pipeline debut, closing a leak batch 8's audit flagged:
`score-batch-2.mjs` now cross-references the combined suppression +
refutations index before scoring, so an already-adjudicated candidate
is excluded and reported rather than silently re-entering a fresh
review lane. On this run, 114 previously-adjudicated (entity_id,
wdid) pairings across 106 companies were auto-excluded, including 3
"zombie" hand-curated exclusions carried forward from batch 8 that
had never been individually adjudicated on their own evidence. Both
new matches are single-WDID; 2 WDIDs added. Now **376 tier-1 verified
company-to-WDID matches**.

- Added (both `matched_on=batch9-promoted-verified`): Gunnison and
  Ohio Creek Canal Company, Richfield Canal Company.
- **Evidence pattern.** Both rest on a statewide-unique structure name
  matching the company's own name, plus an in-rule
  appropriation-to-incorporation date chain: Gunnison and Ohio Creek
  Canal Company's 18-day gap is the tightest found across any
  promotion batch to date; Richfield Canal Company's ~16-month gap is
  corroborated by a statewide Secretary of State search returning
  exactly one water-associated entity for "Richfield."
- Of this batch's 28 lane1 adjudications (26 companies / 34 WDIDs
  individually reviewed): 2 MATCH (both promoted, above), 6 REJECT,
  19 NEEDS_MORE, 1 NEEDS_MORE_STILL — nothing was stretched to a
  promotion on a bare structure-name match alone. Zero verifier
  overturns across all 28.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- Full adjudication record is in
  `water/audits/2026-08-09-match-batch9.md` in the DitchBook repo.

## [1.5.0] — 2026-08-08

7 companies added via promotion batch 8 (two independently-sourced
adjudication tracks — fresh discovery via a structure-name-exact
channel, plus evidence-closure on carryovers from batches 6 and 7 —
cross-examined by a third, adversarial review pass before promotion).
All 7 are single-WDID matches; 7 WDIDs added. Now **374 tier-1
verified company-to-WDID matches**.

- Added (all `matched_on=batch8-promoted-verified`): Beaver Farmers
  Canal And Ditch Company, Dave Miller Mutual Ditch Company, Dixon
  Canon Ditch And Reservoir Company, Hermosa Company Ditch,
  Mitchell-Cooper Ditch And Pipeline Company, High Line Canal Company,
  Mayham Reservoir Corporation.
- **Evidence pattern.** Each match rests on a statewide-unique
  structure name (a company-form name, a personal name, or a namesake
  drainage) plus independent corroboration: SoS-address-to-structure
  geographic concordance, an appropriation-to-incorporation date
  chain, or — for the two evidence-closure carryovers, High Line Canal
  Company and Mayham Reservoir Corporation — a DWR AKA company-code
  decode and county-level SoS/contact concordance.
- **One track-level match declined, not promoted:** Sunny Slope
  Reservoir Company cleared an initial match but was declined on
  evidence-custody grounds by the adversarial review — recorded in the
  adjudication trail, not published.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- Full adjudication record is in
  `water/audits/2026-08-08-match-batch8.md` in the DitchBook repo.

## [1.4.0] — 2026-08-05

Two releases in one version bump: +16 companies / +43 WDIDs total. Now
**367 tier-1 verified company-to-WDID matches**.

- **Promotion batch 7 (+15 companies / +42 WDIDs)**, drawn from the
  abbreviation-variant cohort: companies DWR's own records name only via
  an abbreviation pattern (e.g. `RES. CO.`, `IRR CO`) that exact-string
  matching missed. Adjudicated across three review passes. Added (all
  `matched_on=batch7-promoted-verified`): Uncompahgre Valley Water Users
  Association, The San Luis Valley Canal Company, Manassa Land And
  Irrigation Company, Fruitland Irrigation Company, Greeley Irrigation
  Company, Upper Platte and Beaver Canal Company, The Lower Platte and
  Beaver Canal Company, Sherwood Irrigation Company, Warren Lake
  Reservoir Company, Schneider Ditch Company, Farmers Pawnee Canal
  Company, Park Reservoir Company, Grant Reservoir Company, Taylor &
  Gill Ditch Company, Beaver Creek Ditch Company.
- **New evidence channel debuts, corroboration-only:** DWR's own
  structure-level AKA facility/company-code field. Never used as the
  sole basis for a promotion — only to confirm or contest an
  attribution reached by other evidence. Its first use caught two wrong
  publications rather than generating new ones, so two companies in
  this batch publish a subset: Uncompahgre Valley Water Users
  Association publishes 20 of 21 dam-cited WDIDs (the Garnet structure
  is held — its aka code names a Garnet company, and two same-name
  Garnet companies exist in the census); Manassa Land And Irrigation
  Company publishes 3 of 4 (one structure's aka code identifies the
  already-published sibling company, Manassa Ditch Company, instead).
- **The Farmers Water Development Company (+1 WDID) — the v1.3.0
  deferral resolved.** WDID `6003507` now publishes. The hold was a
  pipeline-mechanics issue, not an evidentiary one: promoting it
  collided with the already-published Naturita Canal And Reservoir
  Company's WDID `6000707` inside the reproducibility pipeline. That
  collision is now fixed with a corrections-ledger constraint applied
  at candidate-generation time; its pin constrains this release's
  publication to the single verified structure. Naturita Canal And
  Reservoir Company's published WDID `6000707` is undisturbed.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- Full adjudication record is in
  `water/audits/2026-08-05-batch7-final.md` in the DitchBook repo.

## [1.3.0] — 2026-08-05

25 companies added via promotion batch 6 (three-pass adversarial review
plus a fourth upgrades mini-review), drawn from a new evidence class:
Colorado Dam Safety's owner-of-record field, cross-checked against DWR
structure records rather than trusted alone, plus primary-document
upgrade chains (water-court decrees, Secretary of State filing
histories) that resolved two held-over matches. 67 WDIDs added. Now
**351 tier-1 verified company-to-WDID matches**.

- Added (all `matched_on=batch6-promoted-verified`): Blue Lake
  Reservoir Company, Boulder And White Rock Ditch And Reservoir
  Company, Cedar Mesa Reservoir Company, Denver-View Reservoir And
  Irrigation Company, Eastdale Mutual Ditch And Reservoir Company,
  Farmers Reservoir And Irrigation Company, Granby Ditch And Reservoir
  Company, Grand Mesa Reservoir Company, Kern Reservoir And Ditch
  Company, Leon Park Reservoir Company, Leroux Creek Water Users'
  Association, Loveland Lake and Ditch Company, Marcot Park Ditch And
  Reservoir Company, Needle Creek Reservoir Association, Paradox
  Valley Canal & Reservoir Co., Sanchez Ditch And Reservoir Company,
  Seven Lakes Reservoir Company, St. Vrain Reservoir And Fish Company,
  Surface Creek Ditch And Reservoir Company, Terror Ditch And
  Reservoir Company, The Tunnel Water Company, Trinchera Irrigation
  Company, Twin Lakes Reservoir And Canal Company, Weir And Johnson
  Ditch And Reservoir Company, West Reservoir And Ditch Company.
- **Subset publication continues.** Grand Mesa Reservoir Company
  publishes 3 of 4 dam-cited WDIDs; the fourth is withheld pending
  independent attribution beyond the dam owner field alone — reasons
  on record in `water/audits/2026-08-05-match-audits.md` in the
  DitchBook repo.
- **Two held-over matches resolved on new primary-document evidence:**
  St. Vrain Reservoir And Fish Company (water-court decrees CA4790 and
  02CW0334) and Surface Creek Ditch And Reservoir Company (a Secretary
  of State filing-history resolution to the 1886 entity over a
  same-name, dormant-since-2016 shell at the same address). Farmers
  Reservoir And Irrigation Company ("FRICO"), deferred during batch 5's
  review over an operator-versus-owner question, is promoted on 5 WDIDs — its own filed
  Articles of Amendment name three of the five structures as its own
  corporate divisions.
- **One adjudicated match deliberately not in this release:** The
  Farmers Water Development Company (WDID 6003507) is evidentially
  sound but held back for a pipeline-mechanics reason, not an
  evidentiary one — promoting it collides with the already-published
  Naturita Canal And Reservoir Company's WDID 6000707 inside the
  reproducibility pipeline (a chain-order defect requiring a reviewed
  code change before it can ship safely). It is adjudicated, not
  suppressed or refuted, and ships in a future release once the fix
  lands.
- **Box Springs Canal And Reservoir Company's two Teller County WDIDs,
  held back since v1.2.0, are now documented as company-specifically
  refuted**: the 1974 decree awards both structures to Robert Markus,
  an individual, not the company. They remain unpublished; this is a
  documentation update to why they're withheld, not a new
  `suppression-list.csv` entry, since they were never published in
  the first place.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- Full adjudication record is in
  `water/audits/2026-08-05-match-audits.md` in the DitchBook repo.

## [1.2.1] — 2026-08-05

One match withdrawn: an out-of-scope entity that should not have been
in the census. Now **326 tier-1 verified company-to-WDID matches**.

- **Removed:** Palisade Irrigation District (published with a blank
  `entity_id`; WDID 7200817, Colorado River, Mesa County). Palisade
  Irrigation District is a Title 37 statutory irrigation district — a
  taxing/assessment authority, not a shareholder-owned mutual ditch
  company — and falls outside the census's own admission rules. It was
  present in the original seed by oversight and is withdrawn now as
  part of a project-wide correction.
- Two further Title 37 districts (Riverside Irrigation District,
  Orchard Mesa Irrigation District) were removed from the census in the
  same correction but carried no published match, so this is the only
  row this release affects.
- No other match's identity, WDID, water source, earliest year, or
  county changed as part of this release.

## [1.2.0] — 2026-08-04

12 companies added via promotion batch 5, following a three-pass
adversarial review (pass 1 evidence assembly, pass 2 independent
adversarial re-derivation, pass 3 reconciliation) — the same
discipline as batch 4. 51 WDIDs added. Now **327 tier-1 verified
company-to-WDID matches**.

- Added (all `matched_on=batch5-promoted-verified`): Big Ditch
  Company, Box Springs Canal And Reservoir Company, Catlin Canal
  Company, Colorado Canal Company, Home Supply Ditch Company Inc.,
  Lake Arrowhead Water Association, Last Chance Ditch Company, Saddle
  Mountain Mutual Water Company, The Fort Lyon Canal Company, The
  United Water Company, The Water Supply And Storage Company, The
  Welton Land and Water Company.
- **Subset publication for multi-county systems.** Five of the twelve
  companies span multiple counties; each WDID for these was verified
  individually rather than published as a block. Box Springs Canal And
  Reservoir Company publishes 5 of 7 WDIDs; Catlin Canal Company
  publishes 1 of 2; Colorado Canal Company publishes 1 of 2; Home
  Supply Ditch Company Inc. publishes 2 of 5 (the other 3 belong to a
  distinct, unrelated company of the same name in a different county);
  Last Chance Ditch Company publishes 1 of 3 (the other 2 belong to
  two further unrelated companies that share the same structure name).
  Withheld WDIDs are not published under any other company either —
  they wait on further evidence.
- No previously published match changed identity, WDID, water source,
  earliest year, or county as part of this release.
- Full adjudication record — including candidates reviewed this batch
  that were not promoted — is in
  `water/audits/2026-08-04-match-audits.md` in the DitchBook repo.

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
