# divvy_bike_share_case_study
Analysis of 12 months of Divvy bike-share data (6.1M rides) comparing annual members vs casual riders: ride length, weekly patterns, seasonality, and bike type. Python, pandas, matplotlib.

### Converting casual riders into annual members

One business question: how do annual members and casual riders
use Divvy differently, and what would make casual riders become members?

Built with Python (pandas, matplotlib) in Jupyter, following the Google
Data Analytics workflow: Ask, Prepare, Process, Analyze, Share.

---

## The Answer in Brief

Members ride for utility. Casual riders ride for leisure. The two groups
differ in when, how long, and how seasonally they ride:
   | Members | Casual riders |
 |---|---|---|
 | Rides (12 months) | 3.95 M | 2.16 M |
 | Average duration | 12 min | 18 min |
 | Busiest days | Wednesday / Thursday | Sunday / Saturday |
 | Seasonal swing (low → high month) | ×4.6 | ×14.5 |
 | Electric-bike share | 68 % | 74 % |

## Recommendations

1. Run conversion campaigns on weekends, when casual riders are on the
   network.
2. Launch offers in early spring, at the start of the casual riding
   season.
3. Market the per-ride economics — translate a casual rider's own usage
   into a cost comparison with annual membership.

## Repository Structure
 | Path | Content |
 |---|---|
 | `notebook.ipynb` | Full pipeline: load, clean, verify, analyze, visualize |
 | `REPORT.md` | Final report: findings, charts, recommendations, limitations |
 | `CLEANING_LOG.md` | Every cleaning rule, defect, and verification result |
 | `ANALYSIS_SUMMARY.md` | Working analysis notes |
 | `analysis/` | Six summary CSVs behind every figure |
 | `figures/` | Chart images used in the report |

## Data Quality

The pipeline verifies itself: zero negative durations, zero rides over
24 hours, zero duplicate ride IDs, zero missing user types. It also
uncovered two genuine source defects — a January 2026 file mislabeled as
January 2025 (caught by inspecting ride dates) and 28 ride IDs duplicated
across month boundaries. Both fixes are documented in the cleaning log.

## Data and Reproduction

Public Divvy tripdata, twelve monthly files (September 2025 –
August 2026). Raw files are not committed due to size; the notebook
rebuilds the entire dataset from the public source. Run it top to
bottom to reproduce every table and figure.
