
# Machine Learning — Learning Playlist (notebooks + datasets)

This repository is organised as a hands-on, sequential learning playlist for someone who wants to learn machine learning from first principles through short notebooks and small projects. It groups small notebooks, datasets, and example scripts into a path you can follow step-by-step.

## Quick start (recommended order)

Follow this order if you're learning ML from scratch. Each step lists the folders/notebooks to open and short goals.

1. Python fundamentals (`Python/`, root notebooks)
  - Goal: get comfortable with variables, control flow, functions and basic data structures.
  - Key files: `Python/` notebooks and the root `pandas-numpy-python-cheatsheet.ipynb` for refresher snippets.

2. Data loading and cleaning (`Data_Gathering/`, `CSV_File/`)
  - Goal: learn how to read CSV/JSON/Excel files, handle encodings, chunked reads, and basic cleaning.
  - Key files: `Data_Gathering/CSV/Working_With_CSV.ipynb`, files inside `CSV_File/` used as practice datasets.

3. Pandas & NumPy (`Pandas/`, `Numpy/`)
  - Goal: master DataFrame manipulation, groupby, reshape, missing data handling, and vectorized ops with NumPy.
  - Key files: `pandas-numpy-python-cheatsheet.ipynb`, `Pandas.ipynb`, and notebooks in `Numpy/`.

4. Exploratory Data Analysis (EDA) (`EDA/`)
  - Goal: perform EDA on real datasets (cleaning, visualization, feature exploration) and produce a simple report.
  - Key files: `EDA/Practice.ipynb`, `EDA/titanic-dataset-prediction.ipynb`.

5. Visualization (`Matplotlib/`)
  - Goal: learn plotting essentials to communicate results—line, bar, scatter, histograms, and basic styling.
  - Key files: notebooks and images under `Matplotlib/`.

6. Machine learning basics with scikit-learn (`Scikit_Learn/`)
  - Goal: learn supervised learning workflow (train/test split, metrics, model fitting) using small datasets.
  - Key files: `Scikit_Learn.ipynb`, use `Books_small.json` and smaller CSVs for examples.

7. Regression projects (`Linear_Regression/`)
  - Goal: implement linear and logistic regression examples and small projects end-to-end (preprocess → train → evaluate → visualize).
  - Key files: notebooks inside `Linear_Regression/`.

8. Toy projects and utilities (`Python_Library/`)
  - Goal: explore small projects and utility code (model save/load, helper functions). Useful for seeing how pieces fit together.
  - Key files: `Python_Library/Toy_Project.ipynb`.

9. Put it together: small end-to-end demos
  - Work through an EDA notebook, then train a model in `Scikit_Learn`, and finally validate it using techniques from `Linear_Regression`.

## How this playlist helps you learn faster

- Bite-sized notebooks: each notebook focuses on one concept (I/O, pandas, plotting, a single model). Work one notebook per session.
- Reuse real files: `CSV_File/` and `Books_small.json` are small datasets for quick iteration without heavy compute.
- Practice loop: read → clean → EDA → feature prep → train → evaluate → iterate.

## Per-folder guide (what to open and why)

- `Python/` — exercises on Python basics. If you are new, start here.
- `Data_Gathering/` — shows practical CSV/JSON loading patterns and encoding/reading tips.
- `CSV_File/` — sample datasets to practice read/clean/merge operations.
- `Pandas/` & `pandas-numpy-python-cheatsheet.ipynb` — core reference for common pandas idioms.
- `EDA/` — step-by-step exploratory workflows and a Titanic example.
- `Matplotlib/` — plotting examples and image outputs used across EDA notebooks.
- `Numpy/` — quick numeric examples and array operations.
- `Scikit_Learn/` — supervised learning examples and minimal model training recipes.
- `Linear_Regression/` — focused projects for regression and simple modeling.
- `Python_Library/` — utilities, toy projects, and demonstration scripts.

## Run instructions

1. Create and activate a virtual environment (recommended).

Windows (PowerShell):
```powershell
python -m venv .venv; .\.venv\Scripts\Activate.ps1
```

2. Install dependencies:
```powershell
pip install -r requirements.txt
```

3. Start Jupyter (or open notebooks in VS Code):
```powershell
jupyter notebook
```

4. Work sequentially using the playlist above. Start with `Python/` notebooks then progress to data loading, pandas, EDA, visualization, and finally modeling.

## Exercises and checkpoints (suggested)

- After `Python/`: implement a small function to calculate accuracy and write unit tests.
- After `Data_Gathering/`: load `aug_train.csv` and produce a cleaned sample of 100 rows.
- After `Pandas/`: group a dataset by a categorical column and plot group sizes.
- After `EDA/`: write a short report (markdown cell) listing 3 features to use for a model and why.
- After `Scikit_Learn/`: train a simple classifier and produce a confusion matrix.

## Notes and tips

- Keep `myenv/` out of version control; create your own venv using `requirements.txt`.
- Some CSV files may require `encoding='latin-1'` or `on_bad_lines='skip'` when loading — examples live in `Data_Gathering/CSV/Working_With_CSV.ipynb`.

## Next steps I can take

1. Create focused `README.md` files inside each major folder with quick-start steps and exact notebook links.
2. Generate short `try-it` commands and small unit tests for a few notebooks.

If you want me to continue, I'll scan each folder and create per-folder README files (one-by-one). Reply: `yes` to proceed or `no` to stop here.

---

Last updated: 2025-09-16

