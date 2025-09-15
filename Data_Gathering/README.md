# Data_Gathering — file I/O and data sources

Purpose: tips and examples for loading CSV, JSON, and other sources robustly (encoding, chunksize, dtype hints, `on_bad_lines`).

- Open this first
- `Data_Gathering/CSV/Working_With_CSV.ipynb` — demonstrates real-world CSV loading problems and fixes.

What to open (other)
- `Data_Gathering/JASON_SQL/Working_With_JASON_SQL.ipynb` — examples using JSON and SQL-like data.

How to use
- Use the CSV notebook when you encounter parsing errors; try `chunksize` to process big files in small batches.

Suggested exercises
- Load `Data_Gathering/CSV/aug_train.csv` using `chunksize=10000` and compute a running mean of a numeric column.

Notes
- This folder is a practical toolkit — copy the patterns into your own projects when dealing with messy files.
