# Scikit-Learn — modeling recipes

Purpose: quick recipes for supervised learning using scikit-learn: splitting data, training, simple pipelines, saving models.

- Open this first
- `Scikit-Learn/.ipynb` — classifiers and regressors examples.

What to open (other)
- `Books_small.json` (root) — small JSON lines dataset used in some examples.

How to use
- Use the small datasets (Books_small.json, subset CSVs) to iterate quickly on models.

Suggested exercises
- Create a minimal pipeline: `SimpleImputer` → `StandardScaler` → `LogisticRegression` and evaluate with cross-validation.

Notes
- Focus on learning the API patterns: `fit`, `predict`, `score`, `pipeline`, and `GridSearchCV`.
