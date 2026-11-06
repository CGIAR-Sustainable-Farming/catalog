# Sustainable Farming catalogue

Metadata for the [Sustainable Farming Data Hub](https://cgiar-sustainable-farming.github.io), using the [CDH metadata standard](https://github.com/CGIAR-Climate-Data-Hub/cdh-metadata-standard).

## Publication status

`records/` contains approved records only. It is initially empty. `drafts/` contains GAIA metadata prepared from public source papers, dashboards and code; these are **not approved dataset releases**. The site links to these drafts separately from its published catalogue.

- **GAIA acid soils:** passes CDH v0.5.0 structural validation. Licensor authority, accountable metadata maintainer, soil observation dates and exact source build remain unconfirmed.
- **GAIA crop responses to lime:** draft has a missing citation date because the cited manuscript remains in preparation. Trial dates (2020 versus 2022), SOC scaling, lab methods and exact source release require confirmation. Do not invent dates to pass validation.

Provisional roles: CIMMYT as producer/licensor; SFP catalogue team as maintainer; João Vasco Silva as source contact. These roles require confirmation before promotion. The drafts document evidence and limitations in their notes. Inclusion does not claim SFP produced these GAIA outputs.

## Review and release

Resolve open source facts and roles, verify licences and asset links, then move an approved version into `records/` through a reviewed pull request. Published records must pass the official CDH v0.5.0 validator. Draft-only changes do not fail CI for known incompleteness; they must not be promoted automatically.

The website rebuilds daily and on manual dispatch. It fetches the latest catalogue commit and records the exact revision in `/upstream-provenance.json`. A failed build preserves the previous deployment. No cross-repository personal access token is required.

## STAC

The website provides an initial empty static STAC root at `/stac/catalog.json`. It is scaffolding, not a populated catalogue or STAC API. Records will enter STAC only after spatial/temporal extents, asset links and metadata mappings are confirmed and validated. The separate ERA–Carob proof-of-concept remains pending release-ready data.

## Rights

Source data retain their individual licences and citations. Draft `license` fields describe source claims; they do not establish unconfirmed licensing authority. No source data files are hosted in this repository.
