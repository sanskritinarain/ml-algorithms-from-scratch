# Linear Regression

## Introduction and Use Case

Linear Regression is one of the most basic and important machine learning algorithms.  
To understand it, let’s take a simple real-world example.

Suppose a venture capitalist firm wants to decide which companies to invest in.  
One way to do this is by **predicting the profit of a company based on its expenses**.

In this example, we mainly focus on **Research and Development (R&D) spending**.  
Even though real investors consider many factors (around 23–27), here we simplify the problem and use **only one variable**.

By plotting **profit vs R&D spending**, we can draw a straight line that helps us estimate future profits.  
The basic idea is that **companies spending more on R&D generally earn higher profits**, so R&D becomes a good indicator.

---

## Machine Learning Overview

This tutorial first introduces machine learning and then focuses on **linear regression**.

Machine learning means teaching a system to learn patterns from data instead of writing rules manually.

One simple example of machine learning is predicting **crop yield based on rainfall**:
- Rainfall is the **independent variable (x)** because we cannot control it.
- Crop yield is the **dependent variable (y)** because it depends on rainfall.

So, the independent variable affects the dependent variable.

---

## Data Types in Machine Learning

There are mainly two types of data used in machine learning:

- **Numerical data**: values like age, salary, height, marks, etc.
- **Categorical data**: values like gender, color, dog breed, etc.

---

## Types of Machine Learning Algorithms

Machine learning algorithms are broadly divided into three types:

1. **Supervised Learning**  
   In this type, the data is already labeled (we know the output).
   Linear regression comes under supervised learning.

2. **Unsupervised Learning**  
   In this type, the data is not labeled and the algorithm tries to find patterns.

3. **Reinforcement Learning**  
   The model learns using rewards and penalties.

Linear regression is a **supervised learning regression algorithm**.

---

## Types of Regression

There are different types of regression:

- **Simple Linear Regression**  
  Uses only one independent variable and forms a straight line.

- **Multiple Linear Regression**  
  Uses more than one independent variable.

- **Polynomial Regression**  
  Forms a curved line instead of a straight one.

---

## Applications of Linear Regression

Linear regression can be used in many real-life applications, such as:
- Predicting economic growth
- Forecasting product prices
- Predicting house prices and sales
- Sports analytics (for example, predicting player performance)

---

## Linear Regression Theory

Linear regression tries to find the **best-fit straight line** between two variables.

The equation of a straight line is:

y = mx + c

Where:
- y is the dependent variable  
- x is the independent variable  
- m is the slope of the line  
- c is the intercept (where the line cuts the y-axis)

The slope shows how much y changes when x changes.

---

## Intuition Behind Linear Regression

Most of the mathematical calculations are done automatically by libraries,  
but understanding the idea behind them is important.

Consider a small dataset:

| x | y |
|---|---|
| 1 | 2 |
| 2 | 4 |
| 3 | 5 |
| 4 | 4 |
| 5 | 5 |

The average value of x is 3 and the average value of y is 4.  
The regression line usually passes close to this average point.

---

## Mathematical Calculation (Basic Idea)

To calculate the regression line, we use summations such as:
- sum of x
- sum of y
- sum of x²
- sum of xy

The formula for slope (m) is:

m = (n∑xy − ∑x∑y) / (n∑x² − (∑x)²)

The formula for intercept (c) is:

c = (∑y − m∑x) / n

For the given data:
- m = 0.6  
- c = 2.2  

So, the final equation becomes:

y = 0.6x + 2.2

---

## Prediction Using the Regression Line and Residuals

Once the regression line is obtained, it can be used to predict values of the dependent variable **(y)** for any given value of the independent variable **(x)**.

For this example, the regression equation is:

y = 0.6x + 2.2

By substituting different values of **x** into this equation, we can calculate the predicted values of **y**.

After making predictions, the predicted values are compared with the actual values from the dataset.  
The difference between the actual value and the predicted value is called a **residual** or **error**.

Residual = Actual value − Predicted value  
Residual = y − y_pred

Residuals show how far each data point is from the regression line:
- A small residual means the prediction is accurate.
- A large residual means the prediction is far from the actual value.

---

### Why Do We Square the Errors?

When calculating the total error, we **square the residuals (y − y_pred)** instead of directly summing them.

We do this for the following reasons:

1. **To avoid cancellation of errors**  
   Residuals can be positive or negative.  
   If we simply add them, positive and negative values may cancel each other and give a misleading result.  
   Squaring ensures all errors are positive.

2. **To penalize large errors more**  
   Squaring increases the effect of large errors more than small ones.  
   This helps the model focus on reducing big mistakes.

3. **To make the math easier for optimization**  
   Squared errors are smooth and differentiable, which makes it easier for algorithms to minimize the error and find the best-fit line.

---

### Sum of Squared Errors (SSE)

The overall error of the model is measured using the **Sum of Squared Errors (SSE)**.

SSE = Σ (y − y_pred)²

A smaller SSE value means the regression line fits the data better.

In this example, the **sum of squared errors is 2.4**, which indicates that the regression line provides a good fit.

Graphically, residuals are shown as vertical distances between the actual data points and the regression line.  
Linear regression aims to position the line in such a way that the **total squared error is minimized**, resulting in the best-fit line.


---

## Conclusion

Linear regression is simple but very powerful.  
It helps us understand relationships between variables and make predictions.

Before moving to complex algorithms, it is important to clearly understand linear regression.


# Simple code using scikit-learn

import numpy as np
from sklearn.linear_model import LinearRegression

##Sample data
X = np.array([1, 2, 3, 4, 5]).reshape(-1, 1)
Y = np.array([2, 4, 5, 4, 5])

##Create model
model = LinearRegression()

##Train model
model.fit(X, Y)

##Coefficients
print("Slope:", model.coef_[0])
print("Intercept:", model.intercept_)

##Prediction
x_new = np.array([[6]])
y_pred = model.predict(x_new)
print("Predicted value:", y_pred[0])

