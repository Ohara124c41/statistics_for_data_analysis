# Analyze A/B Test Results

This subproject completes the Udacity A/B testing notebook for the e-commerce landing page experiment. All cells are filled, validated, and runnable.

- Notebook: `analyze_ab_test_results_project.ipynb`
- Data: `ab_data.csv`
- Extras: slide-ready counts (variant/control totals) and a country bar chart added near the Part I descriptive section.

## How to run
1) Open `analyze_ab_test_results_project.ipynb`.
2) Run all cells. Outputs include descriptive stats, probability questions, simulation-based hypothesis test, and final interpretation.
3) Use nbconvert if you want a quick rerun headlessly:
```bash
python -m nbconvert --to notebook --execute --inplace analyze_ab_test_results_project.ipynb
```

## Key results (for slides)
- Total rows: 69,889
- Overall conversion: 0.13048
- Control conversion: 0.10525
- Treatment conversion: 0.15532
- Observed lift (treatment - control): 0.05007
- One-sided p-value (null both pages equal): ~0.0 → reject H0; treatment better at α=0.05
- Country conversion rates: US 0.13277, UK 0.12512, CA 0.12529 (differences small)
- Country x group conversions (Control/Treatment): US 10.7% / 15.8%, UK 10.2% / 14.9%, CA 9.4% / 15.4%
- Totals: Variant visitors = 35,205; Control participants = 34,684; sum matches rows

## Visuals
- Two bar charts are in the notebook: country visits (original) and a “slide-ready” country bar chart.
- Null simulation histogram with observed difference overlay for the A/B test.

## Validation notes
- Checks for missing values (none) and binary `converted` values only.
- Null simulation uses 500 draws; p-value computed one-sided per rubric.
- Extra cells include assertions (counts sum to total rows) for quick sanity checks.***
