# Cleaning Log — Divvy Case Study

Dataset: Divvy tripdata, 12 monthly files, September 2025 - August 2026.
Purpose: document every cleaning rule applied, every data-quality issue
found, and the final verification results.

## 1. Cleaning Rules Applied
- Column names standardized across monthly files (member_casual ->
  user_type).
- started_at / ended_at parsed as datetime.
- ride_length computed in minutes as (ended_at - started_at).
- day_of_week, day_name and month derived from started_at.
- Rows removed when any of ride_id, started_at, ended_at, user_type is
  missing.
- Rides with ride_length <= 0 minutes (data entry errors, ended before
  started) removed.
- Rides with ride_length >= 1440 minutes (24 hours, bikes not returned
  or system errors) removed.
- Duplicate ride_ids within each monthly file removed.

## 2. Data-Quality Issues Found and Fixed
- January 2026 source zip contained a mislabeled CSV (named
  202501-divvy-tripdata.csv); identified by inspecting ride dates
  (2026-01-01 to 2026-01-31), renamed to 202601-divvy-tripdata.csv.
- 28 duplicate ride_ids appearing across two different source months
  were removed after concatenation.
- Six stale analysis CSVs from an earlier export (run on broken
  January data) were deleted from analysis/ to avoid confusion.

## 3. Per-Month Cleaning Summary
| Month | Rows before | Rows after | Removed |
|---|---|---|---|
| 202509 | 714,759 | 714,141 | 618 |
| 202510 | 646,039 | 645,440 | 599 |
| 202511 | 356,628 | 356,262 | 366 |
| 202512 | 140,534 | 140,409 | 125 |
| 202601 | 137,787 | 137,596 | 191 |
| 202602 | 201,450 | 201,333 | 117 |
| 202603 | 317,037 | 316,771 | 266 |
| 202604 | 448,252 | 447,898 | 354 |
| 202605 | 653,704 | 653,131 | 573 |
| 202606 | 762,550 | 761,870 | 680 |
| 202607 | 869,051 | 868,271 | 780 |
| 202608 | 868,191 | 867,521 | 670 |

## 4. Final Verification
- 0 rides with length <= 0 minutes
- 0 rides >= 24 hours
- 0 duplicate ride_ids
- 0 missing user_type
- Final dataset: 6,110,615 rides across 12 months (Sep 2025 - Aug 2026)

All checks passed. Dataset saved as
processed/divvy_2025_2026_cleaned.csv.
