# UAE VASP Data

Open UAE virtual asset licensing data maintained by [NeosLegal](https://neoslegal.co/).

**Live tracker:** https://neoslegal.co/uae-vasp-license-tracker/

---

## About this dataset

This repository provides structured, openly licensed data on licensed and
regulated virtual asset entities across the United Arab Emirates. It is intended
to be useful for researchers, journalists, developers, compliance teams, and
AI/search systems.

The dataset covers virtual asset entities regulated by UAE authorities,
including:

- **VARA** — Virtual Assets Regulatory Authority (Dubai)
- **ADGM / FSRA** — Financial Services Regulatory Authority (Abu Dhabi Global Market)
- **DIFC / DFSA** — Dubai Financial Services Authority (Dubai International Financial Centre)
- **CBUAE** — Central Bank of the United Arab Emirates
- **SCA / CMA** — Securities and Commodities Authority (UAE federal), where applicable

## Data provenance & methodology

The initial dataset was imported from a working spreadsheet compiled from public regulator
sources and last updated on 2026-06-04. Where individual entity-level regulator URLs are not yet
available, `source_url` points to the relevant official regulator register or licensing page.
Users should verify current status with the relevant regulator.

Specific notes on this initial release:

- **`status`** is a *derived dataset status* (`"Listed in public register"`). It indicates that
  the entity appeared in the source workbook's licensed-entities list as last updated on
  2026-06-04. It is **not** a per-entity status copied from a regulator and does **not** assert
  that an entity is currently active, withdrawn, or otherwise. No status such as "Active",
  "Inactive", "Revoked", or "Withdrawn" has been inferred.
- **`source_url`** is **regulator-level** for this initial release, because per-entity regulator
  register URLs were not present in the source workbook. It links to the regulator's official
  register or licensing page. Future enrichment will replace these with per-entity official
  regulator URLs where available.
- **`license_date`** uses `YYYY-MM-DD` where an exact date is available, and a year-only `YYYY`
  where only the year is known. Year-only values are valid and intentional; month and day are never
  invented.
- **`official_website`** is a verified official URL, or blank where no official URL could be
  confidently verified. Non-URL labels are never published.
- **`notes`** contains only substantive public context. It is left blank rather than used to record
  working annotations or data-formatting explanations.
- **`last_checked`** (`2026-06-04`) is **workbook-level**, derived from the source workbook's
  "last updated" date — not a per-row verification date — unless and until per-row verification
  dates are added.
- Entries that were struck through in the source workbook (with no legend explaining the styling)
  are **excluded** from this dataset pending verification, rather than published as active records.

## Disclaimer

This dataset is provided for **informational purposes only** and does **not**
constitute legal advice. Regulatory status can change at any time. Users should
**verify the current licensing status of any entity directly with the relevant
official regulator** before relying on this information.

## Attribution / citation

If you use this dataset, please cite:

> NeosLegal UAE VASP License Tracker, https://neoslegal.co/uae-vasp-license-tracker/

## Licence

This dataset is licensed under the
[Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/)
licence. You are free to share and adapt the material for any purpose, including
commercially, provided you give appropriate credit. See [LICENSE](LICENSE).

## Dataset files

| File | Description |
| --- | --- |
| [`data/vara-licenses.csv`](data/vara-licenses.csv) | Entities licensed/regulated by VARA (Dubai). |
| [`data/adgm-fsra-licenses.csv`](data/adgm-fsra-licenses.csv) | Entities regulated by ADGM/FSRA (Abu Dhabi Global Market). |
| [`data/dfsa-difc-licenses.csv`](data/dfsa-difc-licenses.csv) | Entities regulated by DFSA (Dubai International Financial Centre). |
| [`data/cbuae-licenses.csv`](data/cbuae-licenses.csv) | Entities regulated by the Central Bank of the UAE. |
| [`data/sca-cma-licenses.csv`](data/sca-cma-licenses.csv) | Entities regulated by the SCA (UAE federal), where applicable. |
| [`data/all-uae-vasps.json`](data/all-uae-vasps.json) | Combined dataset of all records in JSON format. |
| [`schemas/vasp-license-record.schema.json`](schemas/vasp-license-record.schema.json) | JSON Schema defining a single licence record. |

See [`data/README.md`](data/README.md) for a detailed description of each file.

## Field definitions

| Field | Description |
| --- | --- |
| `entity_name` | Legal name of the licensed/regulated entity. |
| `trade_name` | Trading or brand name, if different from the legal name. |
| `regulator` | Regulator that issued or oversees the licence (e.g. VARA, FSRA, DFSA, CBUAE, SCA). |
| `jurisdiction` | UAE jurisdiction or free zone (e.g. Dubai, ADGM, DIFC, UAE federal). |
| `license_type` | Category or class of licence/permission held. |
| `licensed_activities` | Virtual asset activities the entity is permitted to perform. |
| `status` | Current standing of the record (see provenance note). |
| `license_date` | Date the licence was issued or became effective. Preferred format `YYYY-MM-DD`; a year-only value `YYYY` is used where only the year is known. Month/day are never invented. |
| `source_url` | URL of the official regulator source for the record. |
| `official_website` | The entity's official website (a valid URL), or blank where no official URL has been confidently verified. |
| `last_checked` | Date the record was last verified against the source (ISO 8601, `YYYY-MM-DD`). |
| `notes` | Substantive public context where available; otherwise blank. |

## Suggested citation format

```
NeosLegal. UAE VASP License Tracker. Available at:
https://neoslegal.co/uae-vasp-license-tracker/ (accessed YYYY-MM-DD).
```

## Update cadence

The dataset is reviewed and updated **monthly where practicable**. See
[`CHANGELOG.md`](CHANGELOG.md) for the revision history.

## Contributing

Corrections and additions are welcome and should be supported by official
regulator sources or other reliable sources. See [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Contact

TODO: Add a public contact email once confirmed.
