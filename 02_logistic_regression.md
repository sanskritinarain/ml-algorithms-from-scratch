# Classification vs Regression & Logistic Regression 

This file is a structured summary of **classification vs regression** and **logistic regression**, based on a YouTube lecture and my own understanding from ML fundamentals.

---

## 1. Supervised Learning – Quick Overview

In **supervised learning**, the model is trained on **labeled data**.

- Input features (X) → known output labels (Y)
- The model learns a mapping from X → Y
- Goal: make accurate predictions on unseen data

Supervised learning is mainly divided into:
- **Classification**
- **Regression**

---

## 2. Classification vs Regression

### Classification
- Predicts **discrete labels**
- Output belongs to a **finite set of classes**

**Examples:**
- Survived / Not survived
- Yes / No
- Spam / Not spam
- Animal type: Cat, Dog, Elephant

#### Types of Classification
- **Binary Classification**  
  Two classes (e.g., survived vs not survived)
- **Multi-class Classification**  
  More than two classes (e.g., digits 0–9, animal categories)

---

### Regression
- Predicts **continuous numerical values**
- Output can be any real number

**Examples:**
- Stock price
- Temperature
- Salary
- Rainfall amount

---

## 3. Why Logistic Regression Is Used for Classification

Even though the name contains *“regression”*, **logistic regression is a classification algorithm**.

Why?
- It predicts **probabilities**, not raw continuous values
- Output is always between **0 and 1**
- These probabilities are converted into **class labels** using a threshold (usually 0.5)

**Example:**
- Output = 0.8 → Class = 1 (Yes)
- Output = 0.3 → Class = 0 (No)

So logistic regression is perfect for **binary classification problems**.

---

## 4. Linear Regression vs Logistic Regression

| Aspect | Linear Regression | Logistic Regression |
|------|------------------|--------------------|
| Purpose | Predict continuous values | Predict class labels |
| Output | Any real value | Probability (0 to 1) |
| Response Variable | Continuous | Discrete (binary) |
| Model Equation | y = β₀ + β₁x | log-odds modeled linearly |
| Curve Shape | Straight line | S-shaped (sigmoid) |
| Example | Salary prediction | Survival prediction |

---

## 5. The Core Problem with Linear Regression for Classification

If we use linear regression for classification:
- Predictions can be **less than 0 or greater than 1**
- These values **cannot represent probabilities**
- No clear decision boundary

So we need:
- Output between 0 and 1
- Interpretable as probability

This is where **sigmoid function** comes in.

---

## 6. Sigmoid Function & Why It Creates an S-Curve

The **sigmoid function** is:

\[
\sigma(z) = \frac{1}{1 + e^{-z}}
\]

### Why sigmoid?
- Converts any real number into a value between **0 and 1**
- Small inputs → output close to 0
- Large inputs → output close to 1

### Why S-shaped curve?
- For very negative values → output saturates near 0
- For very positive values → output saturates near 1
- Middle region is sensitive → **learning happens most here**

This makes it ideal for **binary decision-making**.

---

## 7. Odds and Log-Odds 

### Probability
\[
p = P(Y=1)
\]

### Odds
\[
\text{odds} = \frac{p}{1 - p}
\]

- If p = 0.8 → odds = 4 (event is 4 times more likely to happen than not)

### Log-Odds
\[
\log\left(\frac{p}{1 - p}\right)
\]

### Why take log of odds?
- Odds range from 0 to ∞
- Log-odds range from **−∞ to +∞**
- This makes it compatible with a **linear model**

So instead of predicting probability directly, logistic regression predicts **log-odds**.

---

## 8. Logistic Regression Model 

Logistic regression models:

\[
\log\left(\frac{p(x)}{1 - p(x)}\right) = \beta_0 + \beta_1 x
\]

Then converts log-odds to probability using sigmoid:

\[
p(x) = \frac{1}{1 + e^{-(\beta_0 + \beta_1 x)}}
\]

### What’s happening here?
1. Linear combination of inputs → β₀ + β₁x
2. Output converted to probability using sigmoid
3. Threshold applied → final class label

---

## 9. Where Learning Actually Happens

Learning happens by:
- Adjusting **β₀ and β₁** to minimize loss
- Logistic regression uses **log loss (binary cross-entropy)**

The model learns:
- How strongly each feature affects the **log-odds**
- Direction (+ / −) of impact on the probability

---

## 10. End-to-End Intuition 

1. Input features go into a linear equation
2. Linear output represents **log-odds**
3. Sigmoid converts log-odds → probability
4. Probability converted to class using threshold
5. Loss function measures error
6. Optimization updates weights
7. Model improves predictions

---

## 11. Practical Applications

- **Titanic Survival Prediction** (survived / not survived)
- **Car Breakdown Prediction** based on service history
- **Weather Prediction**
  - Rain / No Rain → Classification
  - Temperature → Regression
- **Image Classification**
  - Dog vs Not Dog
- **Healthcare**
  - Patient survival prediction
  - Disease presence detection

---

## 12. Key Takeaways

- Classification predicts **labels**, regression predicts **numbers**
- Logistic regression is a **classification algorithm**
- Sigmoid ensures valid probability output
- Log-odds allow linear modeling
- Simple math + strong interpretability = powerful baseline model

---
