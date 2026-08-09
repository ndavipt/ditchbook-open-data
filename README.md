# DitchBook — Colorado ditch company to WDID matches (tier-1)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.21711149.svg)](https://doi.org/10.5281/zenodo.21711149)


## Overview

Verified matches between Colorado mutual ditch and reservoir companies
(as registered with the Colorado Secretary of State) and their water
structures (WDIDs) in Colorado DWR records — the organization-to-WDID
relationship that public state datasets stopped exposing directly.
**376 companies** are matched at tier-1: published only where state
records agree beyond doubt, with a citation URL to the underlying DWR
record on every row. Ambiguous candidates are excluded, not guessed.

The matches power the free public registry at
[getditchbook.com](https://getditchbook.com/) — every row's company has
a public profile page, and the full pipeline is documented at
[getditchbook.com/methods/](https://getditchbook.com/methods/). This
package also includes a public suppression list — the record of
matches that were published and later withdrawn (see "Suppressed
matches," below).

## Data dictionary

### `ditchbook-company-wdid-matches.csv`

One row per matched company:

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

### `suppression-list.csv`

One row per withdrawn match — see "Suppressed matches," below, for what
this file is and why it's here:

| Column | Meaning |
|---|---|
| `entity_id` | Colorado Secretary of State business-entity ID of the company whose match was withdrawn. |
| `company_name` | Company name as registered with the Colorado SoS, at the time of demotion. |
| `wdids` | The DWR structure ID(s) the withdrawn match covered. |
| `demoted_date` | Date the match was removed from publication. |
| `reason` | Short code for why the match was withdrawn (e.g. `basin-county-conflict`). |
| `reference` | Free-text provenance note — the internal review record and, where applicable, a pointer to where the withdrawal was disclosed publicly. Kept as-is rather than cleaned up, on the same transparency-over-tidiness principle as `matched_on` above. |

### `changes-keyed.csv`

The cell-level manifest of DitchBook's contribution of these matches
back to the seed dataset (the pull request to OWF's
`owf-data-co-ditch-and-reservoir-companies`): one row per changed
cell, keyed by company name and `BusinessEntity_ID`, with column, old
value, and new value — 660 rows covering the 300 matched companies.
Included so the contribution can be applied or audited against the OWF
master workbook independently of the pull request itself.

## Methodology

Every row is produced by the same pipeline that builds the public
registry: the census (Colorado mutual ditch and reservoir companies) is
reconciled monthly against Colorado Secretary of State business-entity
data for company identity and standing, then matched to Colorado DWR
CDSS structures by entity identity or unique exact normalized name,
with basin-consistency checks. Only matches that clear the tier-1
bar — where the state's own records agree beyond doubt — are published
here; every row carries a citation URL back to the source DWR record so
any match can be checked independently. Full methodology, including
what disqualifies a match and where the known gaps are, is documented
at [getditchbook.com/methods/](https://getditchbook.com/methods/).

## Suppressed matches: a public record, not deleted

When post-publication review finds a conflict in a previously published
match, the row is removed from `ditchbook-company-wdid-matches.csv` —
but the removal itself is not silent. `suppression-list.csv`, included
in this package, is the public record of every match DitchBook has
published and then withdrawn: which company, which structure, when,
and why.

A few things follow from that:

- **Rows are never removed from `suppression-list.csv`.** Once a
  withdrawal is recorded there, it stays — removing it would silently
  re-publish a claim that was already retracted, which is the one
  thing this file exists to prevent.
- **It isn't just documentation — DitchBook's own matching pipeline
  enforces it.** The tooling that produces
  `ditchbook-company-wdid-matches.csv` refuses to run at all if this
  file is missing, unreadable, or malformed, specifically so a
  withdrawn match can never be silently regenerated and re-published
  on a later run.
- **Five matches are recorded here as of this release**: three demoted
  2026-07-21 after a basin-conflict audit found they didn't hold up, a
  fourth (Park Ditch Company) withdrawn 2026-07-27, before this
  dataset's first publication, after pre-release review found the DWR
  match named a different, similarly-named company, and a fifth
  (Palisade Irrigation District) withdrawn 2026-08-05 after the entity
  was found to be a Title 37 statutory irrigation district — out of the
  census's own scope — rather than a shareholder-owned mutual ditch
  company. None are present in `ditchbook-company-wdid-matches.csv`.

See `CHANGELOG.md` for how this connects to version history.

## Update cadence

The registry refreshes monthly against Secretary of State data; matches
grow as verification clears the backlog. Published versions of this
dataset are dated; material changes (additions, demotions) are noted in
`CHANGELOG.md`.

## Attributions

- Seed list: Open Water Foundation,
  [`owf-data-co-ditch-and-reservoir-companies`](https://github.com/OpenWaterFoundation/owf-data-co-ditch-and-reservoir-companies) —
  the open data this project grew from, gratefully credited.
- Company registrations and standings: Colorado Secretary of State
  business-entity data.
- Water rights and structures: Colorado DWR / CDSS public records.
- DARCA membership context: Ditch and Reservoir Company Alliance.

## License

Released under a **Creative Commons Attribution 4.0 International
license (CC BY 4.0)** — use, share, and adapt, including commercially,
as long as you credit "DitchBook (getditchbook.com)". Full legal text
in [`LICENSE`](./LICENSE).

## How to cite

> DitchBook, "Colorado ditch company to WDID matches (tier-1)",
> doi:10.5281/zenodo.21711149,
> getditchbook.com/methods/, data as of 2026-08-09.

## Versioning

This is **v1.6.0**, published 2026-08-09. See
[`CHANGELOG.md`](./CHANGELOG.md) for release history; demotions and
corrections are recorded there, not silently dropped.

## Disclaimer

This is a compilation of public records, offered in good faith with a
citation on every row so any claim can be checked at the source.
DitchBook is not affiliated with any listed company, the State of
Colorado, or DARCA. No warranty; verify against the cited state record
before relying on a row for any consequential purpose. Errors reported
to the maintainer are corrected same-day.

## Maintainer

Nick Davis — DitchBook, getditchbook.com
nick@getditchbook.com · (970) 460-6532
