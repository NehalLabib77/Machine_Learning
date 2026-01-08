# � Data Science Methods Reference

Quick reference guide for methods and functions used in **Pandas, NumPy, Matplotlib, and Seaborn** notebooks.

---

## 🐼 Pandas: Data Manipulation & Analysis

### 📥 Data Loading & Inspection

| Method | Purpose |
|--------|---------|
| `read_csv()` | Load data from CSV files |
| `head() / tail()` | View first/last rows |
| `info()` | Display data types and missing values |
| `describe()` | Get statistical summary |
| `shape` | Get dimensions (rows, columns) |
| `columns / index` | Access column/row names |
| `dtypes` | Check data types |
| `value_counts()` | Count unique values |
| `isnull().sum()` | Count missing values |

### 🔍 Selection & Filtering

| Method | Purpose |
|--------|---------|
| `df['col']` | Select single column |
| `df[['col1', 'col2']]` | Select multiple columns |
| `loc[]` | Label-based row selection |
| `iloc[]` | Position-based row selection |
| `df[df['col'] > value]` | Boolean filtering |
| `query()` | SQL-like filtering |

### ✏️ Column Operations

| Method | Purpose |
|--------|---------|
| `df['new_col'] = ...` | Create new column |
| `drop()` | Remove columns/rows |
| `rename()` | Rename columns |
| `apply()` | Apply function to column |
| `to_datetime()` | Convert to datetime |
| `.dt.year / .dt.month` | Extract date components |

### 📊 Aggregation & Reshaping

| Method | Purpose |
|--------|---------|
| `sort_values()` | Sort rows by column(s) |
| `groupby() + agg()` | Group and summarize |
| `pivot() / pivot_table()` | Reshape data |

### 🔗 Combining & Cleaning

| Method | Purpose |
|--------|---------|
| `merge()` | Join DataFrames (SQL-like) |
| `concat()` | Combine rows/columns |
| `duplicated()` | Identify duplicate rows |
| `drop_duplicates()` | Remove duplicates |
| `fillna()` | Fill missing values |
| `dropna()` | Remove missing values |
| `interpolate()` | Estimate missing values |

### 💾 Utilities

| Method | Purpose |
|--------|---------|
| `to_csv()` | Save to CSV |
| `copy()` | Create data copy |
| `iterrows()` | Iterate through rows |

---

## 🔢 NumPy: Numerical Computing

### 📦 Array Creation

| Method | Purpose |
|--------|---------|
| `array()` | Create array from list |
| `zeros() / ones()` | Create filled arrays |
| `arange() / linspace()` | Create range arrays |
| `full() / full_like()` | Create with specific value |
| `identity()` | Create identity matrix |
| `random.rand() / randint()` | Generate random numbers |

### 📐 Array Properties & Inspection

| Property | Purpose |
|----------|---------|
| `shape / ndim` | Dimensions |
| `dtype / size` | Data type and element count |
| `itemsize / nbytes` | Memory usage |

### 🔧 Array Operations

| Method | Purpose |
|--------|---------|
| `reshape()` | Change array shape |
| `repeat() / concatenate()` | Duplicate and combine |
| `where()` | Conditional selection |
| `sort()` | Sort elements |

### 🧮 Mathematical Operations

| Category | Methods |
|----------|---------|
| **Arithmetic** | `add(), subtract(), multiply(), divide()` |
| **Power/Trig** | `power(), sin(), cos()` |
| **Statistics** | `mean(), median(), std(), var(), min(), max()` |
| **Linear Algebra** | `dot()`, `@` (matrix multiply) |

### 📁 Input/Output

| Method | Purpose |
|--------|---------|
| `genfromtxt()` | Load data from text file |

---

## 📊 Matplotlib: Static Visualizations

### 🖼️ Figure & Layout

| Method | Purpose |
|--------|---------|
| `subplots()` | Create figure with axes grid |
| `tight_layout()` | Auto-adjust spacing |
| `show()` | Display plot |
| `figsize` | Set figure dimensions |

### 📈 Plot Types

| Method | Purpose |
|--------|---------|
| `plot()` | Line plot |
| `scatter()` | Scatter plot |
| `bar() / barh()` | Bar chart (vertical/horizontal) |
| `hist()` | Histogram |
| `pie()` | Pie chart |

### 🎨 Styling & Annotations

| Method | Purpose |
|--------|---------|
| `set_title() / set_xlabel() / set_ylabel()` | Add labels |
| `legend()` | Add legend |
| `grid()` | Add grid lines |
| `colorbar()` | Add color scale |
| `set_xlim() / set_ylim()` | Set axis ranges |

---

## 🎨 Seaborn: Statistical Visualizations

### 📊 Relational Plots

| Method | Purpose |
|--------|---------|
| `scatterplot()` | Scatter with styling |
| `lineplot()` | Line with styling |
| `relplot()` | Multi-plot relational |

### 📈 Distributions

| Method | Purpose |
|--------|---------|
| `histplot()` | Histogram with KDE |
| `kdeplot()` | Kernel density plot |
| `displot()` | Distribution figure |
| `jointplot()` | Bivariate + marginal |

### 📦 Categorical Plots

| Method | Purpose |
|--------|---------|
| `barplot()` | Bar with statistics |
| `boxplot()` | Box plot |
| `violinplot()` | Violin plot |
| `stripplot() / swarmplot()` | Point plots |
| `countplot()` | Count frequencies |

### 📉 Regression & Correlation

| Method | Purpose |
|--------|---------|
| `regplot()` | Regression scatter |
| `lmplot()` | Regression with facets |
| `heatmap()` | Correlation matrix |
| `clustermap()` | Clustered heatmap |

### 🔀 Multi-Plot Layouts

| Method | Purpose |
|--------|---------|
| `pairplot()` | Compare all pairs |
| `FacetGrid()` | Subplot grid by category |

### 🎨 Styling

| Method | Purpose |
|--------|---------|
| `set_style()` | Change plot theme |
| `set_palette()` | Change color scheme |
| `set_context()` | Change scale (paper, talk, poster) |
| `load_dataset()` | Load example datasets |

---
