# Polynomial Regression Notebook

This notebook demonstrates the implementation of polynomial regression using synthetic quadratic data. It compares linear regression with polynomial regression of degrees 2 and 3 to show how polynomial features can better capture non-linear relationships in the data.

## Overview

The notebook explores polynomial regression, a form of regression analysis where the relationship between the independent variable (X) and the dependent variable (y) is modeled as an nth degree polynomial. This is particularly useful when the data shows a curved relationship that linear regression cannot adequately capture.

## What Was Done

### 1. Data Generation
- Generated synthetic quadratic data using NumPy
- X values range from -3 to 3
- y = 0.5 * X² + 1.5 * X + 2 + random noise
- This creates a parabolic relationship with some noise

### 2. Data Visualization
- Plotted the synthetic data points to visualize the quadratic pattern

### 3. Linear Regression Baseline
- Split the data into training and testing sets (80/20 split)
- Applied standard linear regression
- Evaluated performance using R² score
- Visualized the linear fit (straight line) against the curved data

### 4. Polynomial Regression (Degree 2)
- Used scikit-learn's PolynomialFeatures to transform the data
- Created polynomial features of degree 2 (including bias term)
- Applied linear regression on the transformed features
- This effectively creates a quadratic model: y = a * X² + b * X + c
- Evaluated the improved R² score
- Visualized the curved fit that better matches the data

### 5. Polynomial Regression (Degree 3)
- Experimented with degree 3 polynomial features
- Transformed both training and testing data
- Fitted linear regression on cubic features
- Made predictions on new data points
- Plotted the results showing the model's ability to capture the underlying pattern

### 6. Model Evaluation
- Used R² score to compare model performance
- Demonstrated how polynomial regression significantly improves upon linear regression for this dataset
- Showed predictions on new, unseen data points

## Key Concepts Demonstrated

- **Feature Engineering**: Transforming input features to capture non-linear relationships
- **Model Comparison**: Linear vs. polynomial regression performance
- **Overfitting Considerations**: Using appropriate polynomial degrees
- **Data Visualization**: Plotting model predictions against actual data

## Libraries Used

- NumPy: For numerical computations and data generation
- Pandas: For data manipulation (imported but not heavily used here)
- Matplotlib: For data visualization and plotting
- Seaborn: For enhanced plotting (imported but not used)
- Scikit-learn: For machine learning algorithms and evaluation metrics

## Results

The notebook shows that:
- Linear regression performs poorly on quadratic data (low R² score)
- Polynomial regression of degree 2 significantly improves performance
- The model can make accurate predictions on new data points
- Visualization helps understand how the model fits the data

This serves as a practical introduction to polynomial regression and feature engineering techniques in machine learning.