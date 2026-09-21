# Analysis Summary — Working Notes

## Dataset
- 6,110,615 rides, 12 months (Sep 2025 - Aug 2026)
- casual: 2,156,104 rides | member: 3,945,411 rides
- All verification checks passed at zero (see CLEANING_LOG.md)

## Key Numbers

### Ride length by user type
| | casual | member |
|---|---|---|
| mean (min) | 17.8 | 12.0 |
| median (min) | 10.8 | 8.6 |

### Share of rides by day of week (%)
| Day | casual | member |
|---|---|---|
| Monday | 16.1 | 10.6 |
| Tuesday | 11.9 | 14.3 |
| Wednesday | 11.4 | 16.0 |
| Thursday | 11.5 | 16.0 |
| Friday | 12.4 | 15.8 |
| Saturday | 15.5 | 14.6 |
| Sunday | 21.1 | 12.7 |

### Monthly rides (count)
| Month | casual | member |
|---|---|---|
| 1 | 24,656 | 112,933 |
| 2 | 41,088 | 160,251 |
| 3 | 87,631 | 229,121 |
| 4 | 131,223 | 316,675 |
| 5 | 244,654 | 408,510 |
| 6 | 307,873 | 454,024 |
| 7 | 357,121 | 511,205 |
| 8 | 346,641 | 520,962 |
| 9 | 264,772 | 449,202 |
| 10 | 223,569 | 421,921 |
| 11 | 98,871 | 257,292 |
| 12 | 28,005 | 112,415 |

### Bike type share (%)
| | casual | member |
|---|---|---|
| electric_bike | 73.7 | 68.1 |
| classic_bike | 26.3 | 31.9 |

## Interpretation
Members: frequent, short, weekday, weather-resistant - commuters.
Casual: longer, weekend, strongly seasonal - leisure riders.
Both prefer electric bikes; casuals slightly more.
