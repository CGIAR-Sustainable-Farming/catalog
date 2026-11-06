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


## Submit a dataset

Use the [SFP submission form](https://github.com/CGIAR-Sustainable-Farming/catalog/issues/new?template=submit-record.yml), or open a pull request. Prepare YAML in the shared [CDH Metadata Generator](https://cgiar-climate-data-hub.github.io/CDH-metadata-app/), copy its output, and paste it into the SFP form. The shared application's Submit button targets CDH, not SFP. Submissions are public; do not include credentials, private evidence or restricted data.

CDH issue forms, the review template, link checks and issue-to-PR workflow are reused from commit `18e5333f7614ab197dc454774fdc26ba47e82371` under Apache-2.0 (see LICENSE). SFP adaptations change destination, pin validation to v0.5.0, isolate each issue branch, and keep automation opt-in. Dataset-specific licences remain separate.

Issue intake works without automation. Automatic PR creation is **not enabled**: configure a GitHub App scoped to this repository with contents and pull-request write permissions, set `APP_ID` and `APP_PRIVATE_KEY` secrets, then set `SUBMISSION_AUTOMATION_ENABLED=true`. Test a valid and invalid submission before announcing automated intake. The app token allows the resulting PR to trigger validation; ordinary workflow tokens do not reliably trigger subsequent workflows.

Link checks run on relevant PRs and weekly. Their inherited treatment of authentication/rate-limit responses is an availability hint, not proof that an asset is publicly readable or cloud optimized. Reviewers must check real reads. Human reviewer assignments and branch protection still need configuration; no upstream CDH personnel have been assigned to SFP without confirmation.

Immediate catalogue-to-site dispatch remains optional pending a narrowly scoped dispatch credential; the existing daily refresh continues without one. No submission automatically merges, uploads source data, or creates STAC assets.
