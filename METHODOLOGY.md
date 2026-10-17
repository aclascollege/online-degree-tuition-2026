# Methodology — Online Degree Tuition 2026

Snapshot date: **2026-10-15**. Prices change; treat as a snapshot, not a live registry.

## Coverage

740 online degree programs at 537 U.S. institutions, across five levels:
online MBA (228), online DBA (38), business bachelor's (299), online BSCS (67),
online MCS (108).

> **Selection criteria not documented in this release.** How the 537 schools and
> 740 programs were chosen (sampling frame, inclusion rules) is not recorded
> here — a gap to be closed in a future update. Do not treat the set as a
> random or exhaustive sample of U.S. online degrees.

## Sources

Every row's `source_url` points to the university's **own official website**
(tuition page, program page, or bursar/registrar page) as captured on
2026-10-15. `verified` records that date for all rows.

## Estimates

587 of 740 rows (`estimate: true`) are **computed, not quoted**: the school
publishes only a per-credit-hour price, so the total was derived as
per-credit price × required program credits. The exact math is shown in each
row's `tuition_note`. Treat estimates as comparisons, not quotes — fees,
residency differentials, and cohort pricing can shift the real total.

## Currency

Figures are in USD. Where a school quoted another currency, the USD figure
uses the exchange rate at time of verification.

## Limitations

- No `raw/` source tables are shipped with this release, so the build is not
  independently reproducible from this repo alone.
- `accreditation` is unfilled for 421 of 740 rows (57%) — missing, not "none".
- Medians quoted in summaries use the standard definition (average of two
  middle values for even-sized samples).
