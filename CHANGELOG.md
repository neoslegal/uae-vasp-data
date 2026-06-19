# Changelog

All notable changes to this dataset are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).
Dates use ISO 8601 (`YYYY-MM-DD`).

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
