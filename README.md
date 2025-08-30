# Python Basics Jupyter Notebook

This project is a comprehensive Jupyter Notebook designed to introduce and demonstrate fundamental Python programming concepts. It is ideal for beginners who want to learn Python through practical examples and explanations.

## Contents

The notebook covers the following topics:

- **Variables and Data Types**: Introduction to variables, strings, integers, floats, and booleans.
- **Basic Arithmetic**: Performing arithmetic operations such as addition, subtraction, multiplication, division, and more.
- **Simple Functions**: Defining and using functions in Python.
- **Conditionals**: Using `if`, `elif`, and `else` statements for decision making.
- **String Operations**: Manipulating and formatting strings.
- **Collections**:
  - **Lists**: Creating, modifying, and accessing list elements.
  - **Sets**: Working with unordered collections of unique elements.
  - **Tuples**: Using immutable ordered collections.
- **Loops**: Iterating over sequences with `for` loops.
- **Built-in Functions**: Utilizing Python's built-in functions like `max()`, `min()`, `sum()`, `len()`, and `sorted()`.
- **String Formatting**: Using f-strings for readable and efficient string formatting.
- **Simple Calculator**: Implementing a basic calculator function.
- **Practice Examples**: Additional code snippets for practice and demonstration.

## How to Use

1. **Clone or Download** this repository to your local machine.
2. **Open the Notebook** (`.ipynb` file) using [Jupyter Notebook](https://jupyter.org/) or [VS Code](https://code.visualstudio.com/) with the Python extension.
3. **Run the Cells** sequentially to see the output and understand each concept.
4. **Modify and Experiment** with the code to deepen your understanding.

## Requirements

- Python 3.x
- Jupyter Notebook or compatible IDE (e.g., VS Code with Jupyter support)

## Getting Started

To launch the notebook, run:
```bash
jupyter notebook
````

## Workspace guide (sectioned)

Below are short, focused README sections for each folder / major file in this workspace, in the order you requested (Python, Matplotlib, Numpy, ...). Each section lists the purpose and direct links so you can open files quickly.

1) Python
- Purpose: beginner Python examples and small exercises (variables, strings, lists, functions, conditionals).
- Key file: [Python/.ipynb](Python/.ipynb)
- Notes: contains the example cells shown in the notebook (variables, collections, simple functions, calculator).

2) Matplotlib
- Purpose: plotting examples and Matplotlib usage.
- Key file: [Matplotlib/.ipynb](Matplotlib/.ipynb)
- Notes: import patterns and basic plotting snippets.

3) Numpy
- Purpose: NumPy basics, array operations, and numeric examples.
- Key files: [Numpy/](Numpy/) (open the notebook files in that folder)
- Notes: refer to the NumPy sections inside the cheatsheet notebook as well.

4) Python_Library
- Purpose: small toy projects demonstrating DataFrame operations and model outputs.
- Key file: [Python_Library/Toy_Project.ipynb](Python_Library/Toy_Project.ipynb)
- Notes: includes pandas DataFrame inspection examples and a LogisticRegression HTML repr.

5) Linear_Regression
- Purpose: linear- and logistic-regression examples and small projects.
- Key files:
  - [Linear_Regression/Toy_Project.ipynb](Linear_Regression/Toy_Project.ipynb)
  - [Linear_Regression/Diabetes_Prediction.ipynb](Linear_Regression/Diabetes_Prediction.ipynb)
  - [Linear_Regression/the pumpkin market.ipynb](Linear_Regression/the pumpkin market.ipynb)
- Notes: training, plotting regression lines, and using sklearn estimators.

6) Data_Gathering
- Purpose: examples for loading CSV/JSON/SQL data and chunked reading.
- Key files:
  - [Data_Gathering/CSV/Working_With_CSV.ipynb](Data_Gathering/CSV/Working_With_CSV.ipynb)
  - [Data_Gathering/JASON_SQL/Working_With_JASON_SQL.ipynb](Data_Gathering/JASON_SQL/Working_With_JASON_SQL.ipynb)
- Notes: demonstrates encoding, on_bad_lines, chunksize, dtype hints, and JSON loading.

7) CSV_File
- Purpose: collected CSV/TSV datasets used across notebooks and demos.
- Key files:
  - [CSV_File/aug_train.csv](CSV_File/aug_train.csv)
  - [CSV_File/BX-Books.csv](CSV_File/BX-Books.csv)
  - [CSV_File/movie_titles_metadata.tsv](CSV_File/movie_titles_metadata.tsv)
  - [CSV_File/model.pkl](CSV_File/model.pkl)
  - [CSV_File/zomato.csv](CSV_File/zomato.csv)
- Notes: some CSVs need encoding='latin-1' or on_bad_lines='skip' as shown in the CSV working notebook.

8) EDA
- Purpose: exploratory data analysis examples (Titanic, practice EDA).
- Key files:
  - [EDA/Practice.ipynb](EDA/Practice.ipynb)
  - [EDA/titanic-dataset-prediction.ipynb](EDA/titanic-dataset-prediction.ipynb)
- Notes: step-by-step EDA, visualization tips, submission CSV creation.

9) Scikit_Learn
- Purpose: quick sklearn examples and reading JSON/Books_small reviews for ML demos.
- Key file: [Scikit_Learn.ipynb](Scikit_Learn.ipynb)
- Notes: shows reading [Books_small.json](Books_small.json) and extracting (reviewText, overall).

10) Pandas & Cheatsheet
- Purpose: extensive pandas + numpy cheat sheet and examples.
- Key files:
  - [pandas-numpy-python-cheatsheet.ipynb](pandas-numpy-python-cheatsheet.ipynb)
  - [Pandas.ipynb](Pandas.ipynb)
- Notes: covers read_csv options, NaN handling, groupby, reshape, and common gotchas (smart quotes in examples).

11) Books_small.json
- Purpose: JSON lines dataset of book reviews used in examples.
- Key file: [Books_small.json](Books_small.json)
- Notes: used by [Scikit_Learn.ipynb](Scikit_Learn.ipynb) to demonstrate json.loads per-line reading.

12) requirements.txt
- Purpose: package list for reproducing the environment.
- Key file: [requirements.txt](requirements.txt)
- Notes: use a virtual environment and pip install -r requirements.txt.

13) myenv
- Purpose: developer-local virtual environment folder (do not commit).
- Key folder: [myenv/](myenv/)
- Notes: ignore in VCS; recreate via requirements.txt.

How to use this sectioned README
- Open the relevant notebook by clicking the links above.
- Follow each notebook cell top-to-bottom.
- For large CSVs, prefer using the examples in [Data_Gathering/CSV/Working_With_CSV.ipynb](Data_Gathering/CSV/Working_With_CSV.ipynb) (encoding, dtype, chunksize).
