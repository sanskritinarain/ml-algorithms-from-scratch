# Naive Bayes Classifier

## 1. Introduction
Naive Bayes Classifier is a **supervised machine learning algorithm** used for **classification problems**.  
It is based on **Bayes’ Theorem**, which calculates the conditional probability of an event occurring given that another event has already occurred.

The algorithm is called **“naive”** because it assumes that all features are **conditionally independent** of each other.

---

## 2. Bayes’ Theorem
Bayes’ Theorem provides a way to update probabilities based on new evidence.

### Formula:
\[
P(A \mid B) = \frac{P(B \mid A) \times P(A)}{P(B)}
\]

Where:
- \(P(A \mid B)\) → Posterior probability  
- \(P(B \mid A)\) → Likelihood  
- \(P(A)\) → Prior probability  
- \(P(B)\) → Evidence (normalization factor)

In classification, the class with the **highest posterior probability** is selected.

---

## 3. Naive Assumption (Conditional Independence)
Naive Bayes assumes that:
- All features are **independent** given the class label

This assumption simplifies calculations and allows fast computation, even though it may not hold true in real-world data.

---

## 4. Placement in Machine Learning
- Learning Type: **Supervised Learning**
- Problem Type: **Classification**
- Category: **Probabilistic Classifier**

Naive Bayes is commonly compared with:
- Decision Trees
- Logistic Regression
- Support Vector Machines (SVM)

---

## 5. Working Principle
For a given data point with multiple features:
1. Calculate prior probability for each class
2. Calculate likelihood of each feature given the class
3. Multiply prior and likelihoods
4. Select the class with the highest probability

Decision rule:
\[
P(Class \mid Features) \propto P(Features \mid Class) \times P(Class)
\]

---

## 6. Simple Probability Illustration (Coin Toss Example)
To understand conditional probability:
- Toss two coins
- Calculate probabilities of outcomes such as getting heads given that at least one coin is heads
- This demonstrates how **prior knowledge** affects probability estimates

This logic directly applies to Naive Bayes classification.

---

## 7. Use Cases of Naive Bayes Classifier
- Email spam filtering
- Face recognition using facial features
- Weather prediction (rainy or sunny)
- Medical diagnosis (cancer, heart disease risk prediction)
- News and document classification
- Recommendation systems

---

## 8. In-Depth Example: Shopping Purchase Prediction

### Dataset Description
- Total rows: 30
- Features:
  - Day: Weekday / Weekend / Holiday
  - Discount: Yes / No
  - Free Delivery: Yes / No
- Target Variable:
  - Purchase: Yes / No

---

### Probability Calculation Example
Condition:
- Day = Holiday
- Discount = Yes
- Free Delivery = Yes

| Event | Probability |
|---|---|
| Probability of Purchase \(P(A)\) | 0.986 (98.6%) |
| Probability of No Purchase | 0.178 (17.8%) |
| Normalized Purchase Likelihood | 84.71% |
| Normalized No Purchase Likelihood | 15.29% |

### Conclusion
Customers are **significantly more likely to purchase** when:
- It is a holiday
- A discount is offered
- Free delivery is available

---

## 9. Types of Naive Bayes Classifier
1. **Gaussian Naive Bayes**
   - Used for continuous data
   - Assumes normal distribution

2. **Multinomial Naive Bayes**
   - Used for text classification
   - Works with word frequencies

3. **Bernoulli Naive Bayes**
   - Used for binary features (0/1)

---

## 10. Advantages
- Simple and easy to implement
- Requires small training datasets
- Works well with high-dimensional data
- Fast and computationally efficient
- Handles missing and irrelevant features well
- Suitable for real-time applications

---

## 11. Limitations
- Assumes feature independence
- Performance may degrade with correlated features
- Zero probability problem (solved using Laplace smoothing)

---

## 12. Summary
Naive Bayes is a powerful yet simple classification algorithm that applies probability theory to predict outcomes efficiently.  
Despite its simplifying assumptions, it performs remarkably well in real-world applications such as text classification and spam detection.

---
