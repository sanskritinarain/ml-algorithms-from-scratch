# Classification vs Regression & Logistic Regression

This repository contains simple and easy-to-understand notes on  
**Classification**, **Regression**, and **Logistic Regression** based on basic machine learning concepts.

---

## Supervised Learning

Supervised learning is a type of machine learning where the model is trained using **labeled data**.

- Input data is provided along with the correct output
- The model learns the relationship between input and output
- It is used to predict results for new data

Supervised learning is mainly divided into:
- Classification
- Regression

---

## Classification vs Regression

### Classification

Classification is used when the output is a **category or label**.

Examples:
- Yes / No  
- Spam / Not Spam  
- Survived / Not Survived  
- Cat, Dog, Elephant  

#### Types of Classification

**Binary Classification**
- Only two classes  
- Example: Yes or No

**Multi-class Classification**
- More than two classes  
- Example: digits from 0 to 9

---

### Regression

Regression is used when the output is a **numerical value**.

Examples:
- Temperature  
- Salary  
- Stock price  
- Rainfall amount  

---

## Why Logistic Regression Is Used for Classification

Logistic regression is a **classification algorithm**, even though the word “regression” appears in its name.

Reasons:
- It predicts probabilities
- Output values lie between 0 and 1
- These probabilities are converted into class labels

Example:
- Probability close to 1 means the positive class
- Probability close to 0 means the negative class

Logistic regression is mainly used for **binary classification problems**.

---

## Linear Regression vs Logistic Regression

| Feature | Linear Regression | Logistic Regression |
|------|------------------|--------------------|
| Output type | Continuous value | Probability |
| Output range | Any number | Between 0 and 1 |
| Used for | Regression problems | Classification problems |
| Curve shape | Straight line | S-shaped curve |
| Example | Salary prediction | Survival prediction |

---

## Why Linear Regression Does Not Work for Classification

Linear regression is not suitable for classification because:
- Output values can be less than 0 or greater than 1
- These values cannot represent probabilities
- There is no clear boundary to separate classes

A function is needed that always produces values between 0 and 1.

---

## Sigmoid Function (Basic Idea)

The sigmoid function converts any number into a value between 0 and 1.

- Very small values give output close to 0
- Very large values give output close to 1

This creates an S-shaped curve and makes it useful for **binary decisions**.

---

## Probability, Odds, and Log-Odds

**Probability**
- Shows how likely an event is to occur

**Odds**
- Compares the chance of an event happening to not happening

**Log-Odds**
- The logarithm of odds

Why log-odds are used:
- Probability values are limited
- Log-odds can take any value
- This allows the use of a linear model

Logistic regression actually learns **log-odds**, not probability directly.

---

## How Logistic Regression Works

1. Input features are given to the model  
2. A linear calculation is performed  
3. Sigmoid function converts the result into probability  
4. A threshold is applied to decide the class  

---

## How the Model Learns

The model learns by:
- Adjusting weights
- Reducing prediction error
- Using a loss function designed for classification

Over time, it learns:
- Which features matter more
- Whether a feature increases or decreases the probability

---

## Real-Life Applications

- Titanic survival prediction  
- Spam email detection  
- Rain or no rain prediction  
- Disease detection in healthcare  
- Image classification tasks  

---

## Key Takeaways

- Classification predicts categories
- Regression predicts numbers
- Logistic regression is used for classification
- Output is a probability value
- Sigmoid keeps output between 0 and 1
- Logistic regression is simple and highly interpretable


