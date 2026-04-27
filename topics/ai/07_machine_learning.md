# Chapter 7: Introduction to Machine Learning

If Data is the fuel, then Machine Learning (ML) is the engine. In this chapter, we move away from Generative AI for a moment to understand the "Classical ML" algorithms that power the analytical side of IT—like fraud detection, resource forecasting, and log classification.

---

## 7.1 The Three Main Flavors of ML
Machine Learning is generally divided into three strategies:

1. **Supervised Learning:** The model learns from labeled data (Input + Answer). You show it 1,000 logs marked "Error" and 1,000 logs marked "Success," and it learns to tell the difference.
2. **Unsupervised Learning:** The model looks at unlabeled data and tries to find hidden patterns or groups (Clustering). Useful for finding "weird" behavior in network traffic that doesn't fit any known category.
3. **Reinforcement Learning:** The model learns by trial and error to achieve a goal, receiving "rewards" for good actions (used in robotics and game-playing AI).

---

## 7.2 Regression vs. Classification
Most engineering problems fall into one of these two buckets:

* **Classification (Discrete):** Choosing a category. 
  * *Example:* "Is this email Spam or Not Spam?" or "Is this IP address a bot?"
* **Regression (Continuous):** Predicting a numerical value.
  * *Example:* "How many milliseconds of latency will we have at 5:00 PM?" or "How many GB of storage will this database need next month?"

---

## 7.3 Training, Validation, and Testing
You never want to test an engine on the same track it used for practice. We split our data to ensure the model actually "understands" the logic rather than just memorizing the answers:
* **Training Set (80%):** The "textbook" the model studies.
* **Test Set (20%):** The "final exam" used to see how the model performs on data it has never seen before.

---

## 7.4 Overfitting: The "Memorization" Trap
Overfitting happens when a model learns the training data *too* well—including the random noise and errors. 
* **The Result:** It performs perfectly on the training data but fails miserably in the real world. 
* **The Fix:** Simplified models, more data, or "Regularization" techniques.

---

## 🛠 Hands-on: Building a Simple Predictor

We will use the `scikit-learn` library to build a simple Linear Regression model that predicts "Execution Time" based on "Input Size."

```python
from sklearn.linear_model import LinearRegression
import numpy as np

# 1. Prepare some dummy data (Input size vs Execution time in ms)
# X = Input size, y = Time
X = np.array([[10], [50], [100], [200], [500]])
y = np.array([5, 25, 52, 101, 250])

# 2. Initialize and "Fit" (Train) the model
model = LinearRegression()
model.fit(X, y)

# 3. Predict the time for a new input size (e.g., 350)
prediction = model.predict([[350]])

print(f"Predicted execution time for size 350: {prediction[0]:.2f} ms")
```

---

> **Note:** Machine Learning works great for numbers and tables, but for complex things like images and human language, we need deeper layers. Chapter 8 covers **Deep Learning & Neural Networks**.
