# Contributing

Thank you for helping improve the **UAE VASP Data** dataset. Accuracy is the
priority of this project, so all contributions are reviewed carefully.

## What we accept

- Corrections to existing records (e.g. status changes, name changes, dates).
- New licence records for entities regulated by a UAE authority.
- Improvements to documentation, schema, or data formatting.

## Evidence requirement

Every correction or addition **must be supported by an official regulator
source or another reliable source.** Acceptable sources include:

- Official regulator registers, public notices, or press releases
  (VARA, FSRA/ADGM, DFSA/DIFC, CBUAE, SCA).
- Official government gazettes or filings.
- The entity's own official communications, where they corroborate a
  regulator record.

Please provide a direct `source_url` for any factual claim. Contributions
without a verifiable source cannot be merged.

## Correction process

1. **Open an issue** describing the record affected and the change requested.
2. **Cite the source.** Include a direct link to the official regulator page or
   other reliable source that supports the change.
3. **Indicate the date** on which you verified the information (`last_checked`).
4. A maintainer will review the submission against the cited source.
5. If verified, the change is merged and recorded in
   [`CHANGELOG.md`](CHANGELOG.md).

You may also submit a pull request directly. Please keep changes focused and
include the supporting source(s) in the description.

## Data standards

- Use ISO 8601 dates (`YYYY-MM-DD`) for `license_date` and `last_checked`.
- Keep entity names as they appear in the official source.
- Do not add speculative, unverified, or invented records.
- Match the column order defined in [`data/README.md`](data/README.md) and the
  [schema](schemas/vasp-license-record.schema.json).

## Conduct

Please keep all communication professional, neutral, and factual.
