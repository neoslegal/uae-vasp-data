# Changelog

All notable changes to this dataset are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Dates use ISO 8601 (`YYYY-MM-DD`).

## [2026-07-31]

### Changed
- **Consolidated URL handling to a single approved URL per record.** The source workbook is now the
  sole authority for entity URLs: each record publishes exactly one URL in `official_website`, taken
  verbatim from the workbook's approved value or hyperlink target. It may point to the entity's own
  website, an official announcement, a regulator page, or another approved source.
- Updated the UAE VASP dataset from the latest source workbook (source last updated 2026-07-30).
  Total public records: 180 (up from 174). `last_checked` updated to 2026-07-31.
- 13 records now carry the workbook's hyperlink target where the cell displayed a label or a second
  URL; 2 records that were previously blank now carry an approved URL.
- Maerki Baumann &Co. Ltd. (ADGM Branch): `license_date` corrected in source, 2026-01-01 →
  2026-01-15.

### Added
- 6 new records across 5 new entities: Revolut Stored Value Services L.L.C (CBUAE),
  BTCS (MIDDLE EAST) LTD (Bitcoin Suisse) (FSRA), Flipster FZE (VARA), Tribe Tokenisation FZE
  (VARA), and YHEGO Virtual Assets Exchange Service L.L.C (VARA, 2 records).

### Removed
- **`source_url` field removed from the public schema**, CSV files, and JSON output. Regulator and
  rulebook URLs are no longer preserved, inferred, or generated. The public schema is now 11
  columns. Documentation and the JSON Schema were updated accordingly. The Elementor tracker snippet
  does not read this field, so no website code change is required.

## [2026-07-01]

### Changed
- Updated the UAE VASP dataset from the latest source workbook. Total public records: 174.
  `last_checked` updated to 2026-07-01. No WordPress/Elementor snippet change required.

### Added
- 1 FSRA record: Maerki Baumann &Co. Ltd. (ADGM Branch).

## [Unreleased]

### Added
- Initial repository structure created.
- Initial data import from working source spreadsheet (source last updated 2026-06-04):
  173 records across VARA (75), ADGM/FSRA (67), DIFC/DFSA (23), CBUAE (5), and SCA (3).
  `source_url` is regulator-level and `last_checked` is workbook-level for this initial release;
  `status` is the derived value "Listed in public register". Struck-through source rows were
  excluded pending verification.

### Changed
- Re-ingested from the human-amended source workbook. Two source-only columns flagged for exclusion
  were kept out of public output as intended, so `notes` is blank. `license_date` now accepts a
  year-only `YYYY` value where only the year is known (4 CBUAE records); the schema no longer treats
  year-only dates as invalid. `official_website` holds verified official URLs or is left blank
  (non-URL labels are not published). `trade_name` is left blank (no dedicated source column).
  One withdrawn entity was removed from the source; struck-through rows remain excluded.
