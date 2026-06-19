# Data files

This directory contains the UAE VASP licensing dataset. Each regulator has a
dedicated CSV file, and a combined JSON file aggregates all records.

> **Initial release provenance.** Records were imported from a working spreadsheet compiled from
> public regulator sources, last updated **2026-06-04**. Please note the following field-level
> conventions for this initial release:
>
> - **`status`** is a derived dataset status (`"Listed in public register"`) meaning the entity
>   appeared in the source workbook's licensed-entities list as of 2026-06-04. It is not a
>   per-entity regulator status and asserts nothing about current activity. No status was inferred.
> - **`source_url`** is **regulator-level** (the regulator's official register/licensing page),
>   because per-entity regulator URLs were not present in the source. Future enrichment will
>   replace these with per-entity official regulator URLs where available.
> - **`license_date`** is `YYYY-MM-DD` where an exact date is available, or a year-only `YYYY` where
  only the year is known (valid; month/day never invented).
- **`official_website`** is a verified official URL, or blank where none could be confidently
  verified. Non-URL labels from the source are not published.
- **`notes`** holds only substantive public context, otherwise blank (no working annotations, no
  formatting explanations).
> - **`last_checked`** (`2026-06-04`) is **workbook-level**, not a per-row verification date,
>   unless and until per-row verification dates are added.
> - Users should verify current licensing status directly with the relevant regulator.
> - Source rows that were struck through (with no legend explaining the styling) are excluded
>   from public output pending verification.

## Files

| File | Regulator | Scope |
| --- | --- | --- |
| `vara-licenses.csv` | VARA | Virtual asset entities licensed/regulated by the Virtual Assets Regulatory Authority (Dubai). |
| `adgm-fsra-licenses.csv` | FSRA (ADGM) | Entities regulated by the Financial Services Regulatory Authority in the Abu Dhabi Global Market. |
| `dfsa-difc-licenses.csv` | DFSA (DIFC) | Entities regulated by the Dubai Financial Services Authority in the Dubai International Financial Centre. |
| `cbuae-licenses.csv` | CBUAE | Entities regulated by the Central Bank of the United Arab Emirates. |
| `sca-cma-licenses.csv` | SCA | Entities regulated by the Securities and Commodities Authority (UAE federal), where applicable. |
| `all-uae-vasps.json` | All | Combined dataset of all records across regulators, conforming to the schema. |

## Columns

All CSV files share the same column structure, in this order:

| Column | Required | Description |
| --- | --- | --- |
| `entity_name` | Yes | Legal name of the licensed/regulated entity. |
| `trade_name` | No | Trading or brand name, if different from the legal name. |
| `regulator` | Yes | Regulator that issued or oversees the licence (VARA, FSRA, DFSA, CBUAE, SCA). |
| `jurisdiction` | Yes | UAE jurisdiction or free zone (e.g. Dubai, ADGM, DIFC, UAE federal). |
| `license_type` | No | Category or class of licence/permission held. |
| `licensed_activities` | No | Virtual asset activities the entity is permitted to perform. |
| `status` | Yes | Current standing of the record (see provenance note above). |
| `license_date` | No | Date the licence was issued or became effective (`YYYY-MM-DD`, or `YYYY` if only the year is known). |
| `source_url` | Yes | URL of the official regulator source for the record. |
| `official_website` | No | The entity's official website (valid URL) or blank. |
| `last_checked` | Yes | Date the record was last verified against the source (`YYYY-MM-DD`). |
| `notes` | No | Substantive public context, otherwise blank. |

## Conventions

- **Encoding:** UTF-8.
- **Dates:** ISO 8601 (`YYYY-MM-DD`); `license_date` may be year-only (`YYYY`) where only the year is known.
- **Empty values:** leave the field blank (no placeholder text).
- **Multiple values** within `licensed_activities` may be separated by a
  semicolon (`;`).
- Field definitions and validation rules are formalised in
  [`../schemas/vasp-license-record.schema.json`](../schemas/vasp-license-record.schema.json).

## JSON format

`all-uae-vasps.json` is a JSON array of record objects. Each object uses the
same field names as the CSV columns. It is currently an empty array (`[]`) and
will be populated as records are verified.
