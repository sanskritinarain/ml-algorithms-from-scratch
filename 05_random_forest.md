# Random Forest 

## 1. Random Forest 

- **Random Forest** is an ensemble learning algorithm.
- It builds **multiple decision trees** and combines their outputs.
- Final prediction is made using **majority voting** (for classification).
- It reduces **overfitting**, which is a common issue in single decision trees.
- Different trees are trained on **different subsets of data and features**, making the model more robust.
- It can handle **missing data** better than many other algorithms.
- Random Forest is **efficient and scalable**, making it suitable for:
  - Remote sensing
  - Object detection
  - Motion tracking (e.g., Microsoft Kinect)

---

## 2. Machine Learning Context

- Random Forest is a **supervised learning algorithm**.
- It is mainly used for **classification** problems.
- Output values are **categorical**, such as:
  - Yes / No
  - Apple / Lemon
  - Setosa / Versicolor / Virginica

---

## 3. Decision Tree Fundamentals

A **decision tree** classifies data by asking questions step-by-step based on feature values.

### Important Terms

- **Entropy**
  - Measures randomness or disorder in data
  - Lower entropy means data is more pure

- **Information Gain**
  - Reduction in entropy after a split
  - Higher information gain means a better split

- **Root Node**
  - Topmost node
  - Contains the entire dataset

- **Decision Node**
  - Node where data splits based on a feature

- **Leaf Node**
  - Final node
  - Gives the class label

### Example

- Fruits are classified using features like:
  - Diameter
  - Color
- Based on these features, fruits such as **apple, lemon, and cherry** are separated.

---

## 4. Random Forest Working

- A Random Forest contains **many decision trees**.
- Each tree:
  - Uses a **random subset of data**
  - Considers a **random subset of features**
- Each tree makes its own prediction.
- The final output is decided by **majority voting**.

### Example

- Tree 1 → Apple  
- Tree 2 → Apple  
- Tree 3 → Lemon  

**Final Prediction → Apple**

---

## 5. Python Implementation (Iris Dataset)

### Data Loading

- Used `load_iris()` from `sklearn.datasets`.
- Iris data includes:
  - Sepal length
  - Sepal width
  - Petal length
  - Petal width
- Data stored in a **Pandas DataFrame**.

---

### Data Preparation

- Added a new column for **species labels**.
- Randomly split data:
  - **75% training data**
  - **25% testing data**
- Converted species names into numeric labels using:
  ```python
  pd.factorize()
