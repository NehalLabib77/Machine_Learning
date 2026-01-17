# 📊 Complete Guide to Linear Regression

A comprehensive guide to understanding and implementing Linear Regression for any dataset, based on practical examples from this repository.

---

## 📚 Table of Contents

1. [What is Linear Regression?](#what-is-linear-regression)
2. [Types of Linear Regression](#types-of-linear-regression)
3. [Step-by-Step Workflow](#step-by-step-workflow)
4. [Code Implementation](#code-implementation)
5. [Performance Metrics](#performance-metrics)
6. [Assumptions & Validation](#assumptions--validation)
7. [Quick Reference Cheat Sheet](#quick-reference-cheat-sheet)

---

## 🎯 What is Linear Regression?

Linear Regression is a **supervised machine learning algorithm** that predicts a continuous target variable based on one or more input features by fitting a straight line (or hyperplane) through the data.

### The Core Equation

**Simple Linear Regression:**
$$y = \beta_0 + \beta_1 x$$

**Multiple Linear Regression:**
$$y = \beta_0 + \beta_1 x_1 + \beta_2 x_2 + ... + \beta_n x_n$$

Where:
- **y** = Predicted value (target/dependent variable)
- **β₀** = Intercept (value when all x = 0)
- **β₁, β₂...βₙ** = Coefficients (slope/weights)
- **x₁, x₂...xₙ** = Features (independent variables)

---

## 📈 Types of Linear Regression

| Type | Features | Use Case |
|------|----------|----------|
| **Simple Linear Regression** | 1 independent variable | Height vs Weight, Price vs Size |
| **Multiple Linear Regression** | 2+ independent variables | House price (size, location, rooms) |

---

## 🔄 Step-by-Step Workflow

```
┌─────────────────┐
│  1. Load Data   │
└────────┬────────┘
         ▼
┌─────────────────┐
│  2. Explore &   │
│     Clean Data  │
└────────┬────────┘
         ▼
┌─────────────────┐
│  3. Feature     │
│     Selection   │
└────────┬────────┘
         ▼
┌─────────────────┐
│  4. Train-Test  │
│     Split       │
└────────┬────────┘
         ▼
┌─────────────────┐
│  5. Feature     │
│     Scaling     │
└────────┬────────┘
         ▼
┌─────────────────┐
│  6. Train Model │
└────────┬────────┘
         ▼
┌─────────────────┐
│  7. Predict &   │
│     Evaluate    │
└─────────────────┘
```

---

## 💻 Code Implementation

### Step 1: Import Required Libraries

```python
import numpy as np
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
%matplotlib inline
```

### Step 2: Load and Explore Data

```python
# Load your dataset
df = pd.read_csv('your_dataset.csv')

# Quick exploration
df.head()           # View first rows
df.info()           # Data types and null values
df.describe()       # Statistical summary
df.isnull().sum()   # Check missing values
```

### Step 3: Exploratory Data Analysis (EDA)

```python
# Visualize relationships between all variables
sns.pairplot(df)

# Check correlation matrix
df.corr()

# Scatter plot for specific features
plt.scatter(df['feature'], df['target'])
plt.xlabel('Feature')
plt.ylabel('Target')

# Regression plot with trend line
sns.regplot(x=df['feature'], y=df['target'])
```

**💡 Tip:** Look for features with **high correlation** to your target variable!

### Step 4: Feature Selection (X) and Target (y)

```python
# ==========================================
# SIMPLE LINEAR REGRESSION (1 feature)
# ==========================================
X = df[['Weight']]    # Double brackets = DataFrame (2D array) ✅
y = df['Height']      # Single brackets = Series (1D array) ✅

# ==========================================
# MULTIPLE LINEAR REGRESSION (2+ features)
# ==========================================
# Method 1: Select specific columns
X = df[['inflation', 'market_demand']]

# Method 2: Select all columns except target
X = df.iloc[:, :-1]   # All columns except last
y = df.iloc[:, -1]    # Last column as target

# Method 3: Drop target to get features
X = df.drop(columns=['target_column'])
y = df['target_column']
```

**⚠️ Important:** X must be a DataFrame (2D), y should be a Series (1D)

### Step 5: Train-Test Split

```python
from sklearn.model_selection import train_test_split

X_train, X_test, y_train, y_test = train_test_split(
    X, 
    y, 
    test_size=0.25,      # 25% for testing
    random_state=42      # For reproducibility
)
```

### Step 6: Feature Scaling (StandardScaler)

```python
from sklearn.preprocessing import StandardScaler

scaler = StandardScaler()

# Fit on training data, transform both
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)  # Only transform, don't fit!
```

**Why Scale?**
- Puts all features on the **same scale** (mean=0, std=1)
- Helps model learn **fairly** from all features
- Improves **convergence speed**

### Step 7: Train the Model

```python
from sklearn.linear_model import LinearRegression

# Create and train model
regression = LinearRegression()
regression.fit(X_train, y_train)

# View model parameters
print("Coefficients (Slopes):", regression.coef_)
print("Intercept:", regression.intercept_)
```

### Step 8: Cross-Validation (Optional but Recommended)

```python
from sklearn.model_selection import cross_val_score

# 5-fold cross-validation
validation_score = cross_val_score(
    regression, 
    X_train, 
    y_train,
    scoring='neg_mean_squared_error',
    cv=5
)

print("Average CV Score:", np.mean(validation_score))
```

### Step 9: Make Predictions

```python
# Predict on test data
y_pred = regression.predict(X_test)

# Predict on new data (remember to scale!)
new_data = [[value1, value2]]  # Your new input
new_data_scaled = scaler.transform(new_data)
prediction = regression.predict(new_data_scaled)
```

---

## 📏 Performance Metrics

### Calculate All Metrics

```python
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

# Error Metrics
mse = mean_squared_error(y_test, y_pred)
mae = mean_absolute_error(y_test, y_pred)
rmse = np.sqrt(mse)

# R-squared
r2 = r2_score(y_test, y_pred)

# Adjusted R-squared
n = len(y_test)                    # Number of observations
k = X_test.shape[1]                # Number of features
adj_r2 = 1 - (1 - r2) * (n - 1) / (n - k - 1)

print(f"MSE:  {mse:.4f}")
print(f"MAE:  {mae:.4f}")
print(f"RMSE: {rmse:.4f}")
print(f"R²:   {r2:.4f}")
print(f"Adj R²: {adj_r2:.4f}")
```

### Understanding the Metrics

| Metric | Formula | Interpretation |
|--------|---------|----------------|
| **MAE** | $\frac{1}{n}\sum\|y_i - \hat{y}_i\|$ | Average absolute error (same units as target) |
| **MSE** | $\frac{1}{n}\sum(y_i - \hat{y}_i)^2$ | Average squared error (penalizes large errors) |
| **RMSE** | $\sqrt{MSE}$ | Square root of MSE (same units as target) |
| **R²** | $1 - \frac{SSR}{SST}$ | % of variance explained (0 to 1, higher = better) |
| **Adj R²** | Adjusted for # features | Better for multiple regression |

---

## ✅ Assumptions & Validation

### The 4 Key Assumptions

1. **Linearity** - Relationship between X and y is linear
2. **Independence** - Residuals are independent
3. **Homoscedasticity** - Constant variance of residuals
4. **Normality** - Residuals are normally distributed

### Validation Code

```python
# Calculate residuals
residuals = y_test - y_pred

# 1. Actual vs Predicted (Check linearity)
plt.scatter(y_test, y_pred)
plt.xlabel('Actual Values')
plt.ylabel('Predicted Values')
plt.title('Actual vs Predicted')
plt.plot([y_test.min(), y_test.max()], [y_test.min(), y_test.max()], 'r--')

# 2. Residual Distribution (Check normality)
sns.displot(residuals, kind='kde')
plt.title('Residual Distribution')

# 3. Residuals vs Predicted (Check homoscedasticity)
plt.scatter(y_pred, residuals)
plt.axhline(y=0, color='r', linestyle='--')
plt.xlabel('Predicted Values')
plt.ylabel('Residuals')
plt.title('Residuals vs Predicted')
```

### Using Statsmodels for Detailed Analysis

```python
import statsmodels.api as sm

# Fit OLS model
model = sm.OLS(y_train, X_train).fit()

# Get comprehensive summary
print(model.summary())
```

The summary provides:
- **R-squared & Adjusted R-squared**
- **F-statistic** (model significance)
- **p-values** for each coefficient
- **Confidence intervals**
- **Durbin-Watson** (autocorrelation test)

---

## 📋 Quick Reference Cheat Sheet

### Complete Pipeline (Copy-Paste Ready)

```python
# ============================================
# LINEAR REGRESSION TEMPLATE
# ============================================

# 1. IMPORTS
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
from sklearn.model_selection import train_test_split, cross_val_score
from sklearn.preprocessing import StandardScaler
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

# 2. LOAD DATA
df = pd.read_csv('your_data.csv')

# 3. EDA
df.info()
df.isnull().sum()
sns.pairplot(df)
df.corr()

# 4. FEATURE SELECTION
X = df.drop(columns=['target_column'])
y = df['target_column']

# 5. SPLIT DATA
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.25, random_state=42)

# 6. SCALE FEATURES
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)

# 7. TRAIN MODEL
model = LinearRegression()
model.fit(X_train, y_train)

# 8. PREDICT
y_pred = model.predict(X_test)

# 9. EVALUATE
print(f"R² Score: {r2_score(y_test, y_pred):.4f}")
print(f"RMSE: {np.sqrt(mean_squared_error(y_test, y_pred)):.4f}")
print(f"MAE: {mean_absolute_error(y_test, y_pred):.4f}")

# 10. VISUALIZE
plt.scatter(y_test, y_pred)
plt.xlabel('Actual')
plt.ylabel('Predicted')
plt.title('Actual vs Predicted')
plt.show()
```

---

## 🎓 Key Takeaways

| Step | Remember |
|------|----------|
| **Features (X)** | Must be 2D DataFrame `df[['col']]` |
| **Target (y)** | Should be 1D Series `df['col']` |
| **Scaling** | `fit_transform()` on train, `transform()` on test |
| **Good R²** | Generally > 0.7 is good, but depends on domain |
| **Residuals** | Should be normally distributed around 0 |

---

## 📁 Files in This Directory

| File | Description |
|------|-------------|
| `Simple_Linear_Regression.ipynb` | Single feature regression example |
| `Multiple_linear_regression.ipynb` | Multiple features regression example |
| `Book1.csv` | Weight-Height dataset |
| `index_price.csv` | Market index dataset |
| `placement.csv` | Placement prediction dataset |

---

## 🔗 Related Topics to Explore

- **Polynomial Regression** - For non-linear relationships
- **Ridge/Lasso Regression** - For regularization
- **Feature Engineering** - Creating better features
- **Outlier Detection** - Handling anomalies

---

*Happy Learning! 🚀*
