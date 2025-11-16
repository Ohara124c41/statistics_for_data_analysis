# Sleep Health & Lifestyle Analysis

Descriptive summary and visuals for the Sleep Health and Lifestyle dataset (374 individuals). The project focuses on sleep outcomes and how activity/vital signs relate to reported sleep disorders.

## Files
- `data/sleep_health_and_lifestyle_dataset-sleep_health_and_lifestyle_dataset.csv` — source data.
- `sleep_health_analysis.ipynb` — executed notebook with all calculations and plots.

## Environment
Python 3.10+ with `pandas`, `numpy`, `seaborn`, `matplotlib`, and `jupyter` (nbconvert is optional for headless runs).

## How to run
```bash
jupyter notebook sleep_health_analysis.ipynb
# or execute headlessly
jupyter nbconvert --to notebook --execute --inplace sleep_health_analysis.ipynb
```

## Key cleaning step
- `Sleep Disorder` had 219 missing entries; these are filled with `"None"` so group comparisons do not drop rows.

## Slide-ready stats (core requests)
- **Data types:** Continuous `Sleep Duration`; Integer `Daily Steps`; Ordinal `Quality of Sleep` (1–10); Nominal `Occupation`.
- **Physical activity (min/day):** mean/median/mode ≈ 59.17/60/60; slight right skew (0.07). By disorder (count | mean/median) — None 219 | 57.95/60; Insomnia 77 | 46.82/45; Sleep Apnea 78 | 74.79/75 (synthetic pattern, not causal).
- **Daily steps:** mean ≈ 6,817; std ≈ 1,618; min 3,000; max 10,000; range 7,000; IQR 2,400. Correlation with sleep quality ≈ 0.017 (no linear link).
- **Sleep duration by disorder (hours):** None 7.36/7.4; Insomnia 6.59/6.5; Sleep Apnea 7.03/6.8.
- **Sleep quality by disorder (rating):** None 7.63/8; Insomnia 6.53/7; Sleep Apnea 7.21/6.
- **Heart rate (bpm):** mean/median/std ≈ 70.17/70/4.14; min 65; max 86; skew 1.22; outliers > ~78 (values 80–86). Boxplot split by disorder included.

## Visuals included in the notebook
- BMI vs sleep disorder stacked proportions (single plot).
- Physical activity: histogram + boxplot by disorder.
- Sleep duration & quality: boxplots by disorder.
- Daily steps: distribution with spread markers + sleep-quality trend plot (color-coded by quality with legend).
- Heart rate: histogram + boxplot by disorder.

## Notes
- Dataset appears synthetic; disorder/activity patterns are descriptive only and not evidence of causation.
