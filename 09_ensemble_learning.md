## What is Ensemble Learning?

Ensemble Learning is a technique where we **combine multiple models** to improve:
- Accuracy  
- Generalization  
- Stability  
- Robustness  

> Instead of trusting one model, we trust the wisdom of many models.

---

## Types of Ensemble Learning

### 1. Bagging (Bootstrap Aggregating)

**Idea:**  
Train multiple models **in parallel** on different random samples of the dataset and combine their predictions.

**Goal:** Reduce variance (overfitting)

**Example:**  
- Random Forest  
- Bagged Decision Trees  

**How it works:**
1. Create random samples (with replacement)
2. Train a model on each sample
3. Combine predictions using:
   - Voting (classification)
   - Averaging (regression)

---

### 2. Boosting

**Idea:**  
Train models **sequentially**, where each new model focuses on correcting the errors of the previous models.

**Goal:** Reduce bias (underfitting)

Popular Boosting Algorithms:
- AdaBoost  
- Gradient Boosting  
- XGBoost  
- LightGBM  
- CatBoost  

---

### 3. Stacking

**Idea:**  
Instead of voting, train a **meta-model** that learns how to best combine predictions from base models.

**Architecture:**
- Level 0: Base models (e.g., Logistic Regression, Tree, KNN)
- Level 1: Meta-model (e.g., Logistic Regression)

---

## Stacking Workflow

1. Train multiple base models  
2. Each base model makes predictions  
3. These predictions become **new features**  
4. A **meta-model** is trained on these predictions  
5. Meta-model produces the final output  

---

## Role of Meta-Model in Stacking

The **meta-model**:
- Takes predictions from base models as input  
- Learns which model to trust in which situation  
- Outputs the final prediction  

> The meta-model does not see original features, only base model predictions.

Common choices:
- Logistic Regression  
- Linear Regression  
- XGBoost  
- Simple Neural Network  

---

## AdaBoost (Adaptive Boosting)

AdaBoost builds a strong model by combining many **weak learners** (usually decision stumps).

### Working:
1. Start with equal weights for all samples  
2. Train a weak learner  
3. Increase weights of misclassified points  
4. Train next learner focusing more on difficult samples  
5. Final prediction = weighted vote of all learners  

### Key Properties:
- Learners are trained **sequentially**
- Each model focuses more on previous mistakes
- Sensitive to noisy data

---
