# Basketball Scoring Probabilities (Steph Curry 2022–23)

This subproject computes the probabilities needed for the four required slides:
- Results of basketball scoring calculations
- Overall Shooting Statistics
- Probabilities (binomial)
- Conditional Probabilities – Future
- Conditional Probabilities – Retrospective

The analysis uses the Kaggle Steph Curry 2022–23 shot dataset located at `data/stephen_curry_shots_2023.csv` and is implemented in the notebook `calculate_basketball_scoring_probabilities.ipynb`.

## How to run
1. Open the notebook: `calculate_basketball_scoring_probabilities.ipynb`.
2. Run all cells (it loads the data, performs EDA, computes probabilities, and renders visuals).
3. Use the printed tables/values for your slide deck.

If you prefer to regenerate the notebook programmatically, run:
```bash
python generate_notebook.py
python -m nbconvert --to notebook --execute --inplace calculate_basketball_scoring_probabilities.ipynb
```

## Key outputs (for slides)
**Overall Shooting Statistics**
- P(Make) = 0.490237 (703 / 1434)
- P(Miss) = 0.509763 (731 / 1434)
- P(Three-pointer) = 0.548117 (786 / 1434)
- P(Two-pointer) = 0.451883 (648 / 1434)

**Probabilities (binomial; assumptions: independence, constant p, fixed n)**
- P(3 makes in next 4) = 0.240241 (k=3, n=4, p=0.490237)
- P(4 of next 5 shots are threes) = 0.203934 (k=4, n=5, p=0.548117)

**Conditional Probabilities – Future (Bayes)**
- P(M | T3) = P(M ∩ T3) / P(T3) = 0.418575
- P(M | T2) = P(M ∩ T2) / P(T2) = 0.577160
- P(L | T3) = P(L ∩ T3) / P(T3) = 0.493639
- P(L | T2) = P(L ∩ T2) / P(T2) = 0.515432

**Conditional Probabilities – Retrospective (Bayes, given a make)**
- P(T3 | M) = P(M ∩ T3) / P(M) = 0.467994
- P(T2 | M) = P(M ∩ T2) / P(M) = 0.532006

## Visuals
The notebook renders:
- Shot outcomes by shot type (bar chart).
_- Shot locations colored by result (scatter)._

These can be exported as slide graphics if desired.

## Data file
- `data/stephen_curry_shots_2023.csv`

## Validation notes
Each section includes simple V&V checks (probability sums to 1 where appropriate, bounds checks on probabilities) to align with the rubric.***
