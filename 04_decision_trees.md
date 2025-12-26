# Decision Tree in Machine Learning 

## Overview
- Decision Trees are **primarily used for classification problems**.
- They can also be used for **regression** tasks.
- Compared to other classifiers:
  - **Naive Bayes** and **Logistic Regression** work well for simpler datasets.
  - **Decision Trees** can handle more complex, non-linear data.
  - **Random Forests** use many decision trees together and are better for large datasets.

---

## How a Decision Tree Works (Simple Idea)
A decision tree works like a flowchart using **if–then rules**.

### Example: Vegetable Classification 
1. Ask a question: **Is the vegetable red?**
   - If **No** → Eggplant (purple)
   - If **Yes** → Check diameter:
     - Diameter > 2 → Bell pepper
     - Diameter ≤ 2 → Chili pepper

This shows how data is split step by step using logical conditions.

---

## Advantages and Disadvantages

### Advantages
- Easy to understand and visualize
- Requires very little data preprocessing
- Works with both numerical and categorical data
- Handles non-linear relationships well

### Disadvantages
- Prone to **overfitting** (learns noise in data)
- High variance (small data change → big tree change)
- Very deep trees may not generalize well

---

## Important Decision Tree Terms

| Term | Meaning |
|---|---|
| **Entropy** | Measure of randomness or impurity in data |
| **Information Gain** | Reduction in entropy after a split |
| **Root Node** | Top-most node of the tree |
| **Decision Node** | Node where data is split |
| **Leaf Node** | Final node with output/class |

---

## Entropy and Information Gain

- **Entropy** tells how mixed the data is  
  - High entropy → more confusion  
  - Low entropy → data is pure  

### Entropy Formula
\[
Entropy = -\sum_{i=1}^{k} p_i \log_2 p_i
\]

- **Information Gain** = decrease in entropy after splitting
- Decision Tree selects the split with **maximum information gain**

---

## Example: Animal Classification
- Dataset contains animals with features like **color** and **height**
- Initial entropy is high (mixed animals)
- Best split is selected using **color**
- Further splits (like height) reduce entropy
- Process continues until entropy becomes zero
- Result: all animals are correctly classified

---

## Practical Use Case: Loan Repayment Prediction

### Objective
Predict whether a customer will **repay a loan** using a decision tree classifier.

---

## Tools and Libraries
```python
import numpy as np
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.tree import DecisionTreeClassifier
from sklearn.metrics import accuracy_score

Load and Explore Dataset
# Load dataset
balance_data = pd.read_csv("loan_data.csv")

# Check shape of dataset
print(balance_data.shape)

# View first 5 rows
print(balance_data.head())

Separate Features and Target
# Feature variables (X)
X = balance_data.values[:, 1:5]

# Target variable (y)
y = balance_data.values[:, 0]

#Split Data into Train and Test Sets
X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.3, random_state=42
)


70% data → training

30% data → testing

random_state=42 ensures same split every time

Build Decision Tree Model
clf_entropy = DecisionTreeClassifier(
    criterion="entropy",
    max_depth=3,
    min_samples_leaf=5
)

Train the Model
clf_entropy.fit(X_train, y_train)

Make Predictions
y_pred = clf_entropy.predict(X_test)

Evaluate Model Accuracy
accuracy = accuracy_score(y_test, y_pred)
print("Accuracy:", accuracy * 100)
``` 
