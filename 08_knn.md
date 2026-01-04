##  Introduction to K-Nearest Neighbors (KNN)

KNN is a **simple yet powerful supervised learning algorithm**.  
It is often one of the first algorithms learners encounter because of its intuitive logic.

### What this guide covers:
- Why KNN is needed
- What KNN is and how it works
- How to choose the parameter **K**
- When to use KNN
- Distance-based classification logic
- A real-world use case: **Diabetes prediction**
- Model evaluation and interpretation

KNN also serves as a **foundation for understanding more advanced ML algorithms**.

---

##  Intuition: Cats and Dogs Classification

Imagine how children distinguish **cats and dogs**:

| Feature | Cat | Dog |
|------|----|----|
| Claws | Sharp | Dull |
| Ears | Small | Big |
| Sound | Meow / Purr | Bark |
| Activity | Calm | Energetic |

When a **new animal** appears, we compare it to animals we already know and decide based on **similarity**.

 **KNN works exactly the same way** — it classifies new data points based on how similar they are to existing labeled data.

---

##  Definition and Core Principle of KNN

- KNN is a **supervised learning algorithm**
- Mostly used for **classification**
- It **stores all training data**
- For a new data point:
  - Finds the **K nearest neighbors**
  - Uses **majority voting** to assign a class

### Example: Wine Classification
If a new wine sample has:
- 4 red wines
- 1 white wine  
among its 5 nearest neighbors →

 The new sample is classified as **red wine**

 Classification depends entirely on **neighbor similarity**, not on a learned equation.

---

##  Understanding the Parameter K

Choosing **K** is called **parameter tuning** and is critical for model performance.

### Effects of K value

| K Value | Effect |
|------|------|
| Too small | Sensitive to noise, overfitting |
| Too large | Over-smoothing, slower computation |
| Optimal | Balanced bias–variance tradeoff |

### Common Rule of Thumb
K ≈ √n

yaml
Copy code
- If √n is even → choose nearest **odd number**
- Odd K avoids **tie situations**

---

##  When Should You Use KNN?

KNN works best when:
- Data is **labeled**
- Dataset is **small to medium**
- Data is **clean (low noise)**
- You want a **quick baseline model**

 KNN is a **lazy learner**:
- No training phase
- All computation happens during prediction

 Not ideal for:
- Very large datasets
- Highly noisy data

---

##  How KNN Works: Distance-Based Classification

KNN uses distance to measure similarity.

### Euclidean Distance Formula
D = √((x − a)² + (y − b)²)

yaml
Copy code

Where:
- (x, y) → new data point
- (a, b) → existing data point

### Classification Steps
1. Calculate distance from new point to all points
2. Select **K nearest neighbors**
3. Use **majority vote** to assign class

---

##  KNN Algorithm Summary

1. Choose value of **K**
2. Compute distances to all training samples
3. Select K closest neighbors
4. Assign class based on majority voting

Simple logic → Powerful results.

---

##  Use Case: Diabetes Prediction Using KNN

### Objective
Predict whether a person has **diabetes**.

### Dataset
- 768 patient records
- Features include:
  - Pregnancies
  - Glucose level
  - Blood pressure
  - Skin thickness
  - Insulin
  - BMI
  - Diabetes pedigree function
  - Age
- Target variable:
  - 0 → No diabetes
  - 1 → Diabetes

Dataset is small and ideal for KNN experimentation.

---

##  Development Environment

- Python 3.x
- Jupyter Notebook
- Anaconda Navigator
- Pip for package management

---

##  Importing Required Libraries

`python
import pandas as pd
import numpy as np

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.neighbors import KNeighborsClassifier
from sklearn.metrics import confusion_matrix, f1_score, accuracy_score

### Loading and Inspecting Data
python
Copy code
data = pd.read_csv("diabetes.csv")
data.head()
len(data)

Handling Missing or Invalid Data
Some features cannot be zero (e.g., glucose, blood pressure).

Strategy
Replace zeros with NaN

Compute column-wise mean

Replace missing values with mean

This prevents bias caused by invalid zeros.

Train-Test Split
python
Copy code
X = data.drop("Outcome", axis=1)
y = data["Outcome"]

X_train, X_test, y_train, y_test = train_test_split(
    X, y, test_size=0.2, random_state=0
)

Feature Scaling (Very Important for KNN)
KNN relies on distance, so features must be scaled.

python
Copy code
scaler = StandardScaler()
X_train = scaler.fit_transform(X_train)
X_test = scaler.transform(X_test)
Prevents large-value features from dominating distance calculations.

Choosing K and Training Model
python
Copy code
k = int(np.sqrt(len(X_train)))
if k % 2 == 0:
    k += 1

knn = KNeighborsClassifier(n_neighbors=k, metric="euclidean")
knn.fit(X_train, y_train)

Model Evaluation
python
Copy code
y_pred = knn.predict(X_test)

confusion_matrix(y_test, y_pred)
accuracy_score(y_test, y_pred)
f1_score(y_test, y_pred)
Example Results
Accuracy: ~80–82%

F1 Score: Useful when false positives and false negatives matter

Accuracy is easy to explain
F1 Score gives deeper insight

Final Summary
What We Learned
KNN uses similarity-based classification

No training phase — lazy learner

Choosing correct K is crucial

Feature scaling is mandatory

Works best on small, clean datasets

Advantages
Simple and intuitive

No complex math

Effective baseline model

Limitations
Slow for large datasets

Sensitive to noise

High memory usage

Key Terms
Term	Meaning
K	Number of neighbors
Euclidean Distance	Straight-line distance
Lazy Learner	No training phase
Parameter Tuning	Choosing optimal K
Imputation	Filling missing values
StandardScaler	Feature normalization
Confusion Matrix	Prediction evaluation
F1 Score	Precision–Recall balance
