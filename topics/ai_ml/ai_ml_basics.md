# AI and ML Basics

## Overview
Artificial Intelligence (AI) and Machine Learning (ML) are transforming IT operations, particularly for Site Reliability Engineers (SREs) working with Kubernetes. This section covers foundational concepts like supervised and unsupervised learning, regression, classification, and neural networks. Understanding these basics is crucial for applying AI to SRE tasks, such as predicting resource usage in Kubernetes clusters or automating incident responses.

## Learning Objectives
- Understand key AI/ML concepts: supervised vs. unsupervised learning, regression, classification, clustering.
- Learn how ML models can predict Kubernetes pod metrics (e.g., CPU, memory).
- Build simple ML models using Python and scikit-learn.
- Apply these concepts to SRE workflows like monitoring and scaling.

## Key Concepts
- **Supervised Learning:** Uses labeled data to train models (e.g., predicting pod CPU usage based on historical metrics).
  - Example: Linear regression to forecast resource demands.
- **Unsupervised Learning:** Finds patterns in unlabeled data (e.g., clustering pods by behavior).
  - Example: K-means clustering to group similar workloads.
- **Classification vs. Regression:** Classification predicts categories (e.g., "pod healthy" vs. "failing"); regression predicts numbers (e.g., memory usage).
- **Neural Networks:** Multi-layered models for complex patterns, foundational for deep learning.
- **SRE Application:** Use supervised learning to predict when a Kubernetes cluster needs scaling or detect anomalies in pod logs.

## Hands-On Exercises
1. **Linear Regression Model:**
   - **Task:** Predict Kubernetes pod CPU usage using a synthetic dataset.
   - **Tools:** Python, scikit-learn, Jupyter Notebook.
   - **Code Example:**
     ```python
     import pandas as pd
     from sklearn.linear_model import LinearRegression
     from sklearn.model_selection import train_test_split

     # Sample data: pod metrics
     data = pd.DataFrame({
         'requests_per_second': [100, 200, 300, 400, 500],
         'cpu_usage': [0.2, 0.4, 0.6, 0.8, 1.0]
     })

     X = data[['requests_per_second']]
     y = data['cpu_usage']
     X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2)
     model = LinearRegression()
     model.fit(X_train, y_train)
     print(f"Predicted CPU usage for 350 req/s: {model.predict([[350]])}")
     ```
   - **Output:** Save the notebook as `linear_regression.ipynb` in this directory.
2. **Clustering Exercise:**
   - Use K-means to group pods by resource usage patterns.
   - Dataset: Generate mock pod metrics (CPU, memory) using `numpy.random`.
   - Save as `kmeans_clustering.ipynb`.

## SRE Applications
- **Resource Prediction:** Use regression to forecast CPU/memory needs, optimizing Kubernetes Horizontal Pod Autoscaler (HPA).
- **Anomaly Detection:** Apply clustering to identify unusual pod behaviors, reducing manual monitoring.
- **Cost Optimization:** Predict resource demands to avoid overprovisioning in cloud clusters.

## Resources
- **Free Course:** [Coursera: AI for Everyone](https://www.coursera.org/learn/ai-for-everyone) (4 weeks, non-technical).
- **Book:** “Hands-On Machine Learning with Scikit-Learn, Keras, and TensorFlow” by Aurélien Géron (Chapter 1-2).
- **Tutorial:** [Scikit-learn Getting Started](https://scikit-learn.org/stable/getting_started.html).
- **SRE-Specific:** “Machine Learning for Site Reliability Engineering” on Pluralsys.

## Next Steps
- Complete the “AI for Everyone” course and commit notes to `notes/ai_for_everyone.md`.
- Build and commit the linear regression notebook to `notebooks/linear_regression.ipynb`.
- Explore classification by modifying the regression script to predict “healthy” vs. “unhealthy” pods.
- Share progress on X with #AIOps #SRE to build your network.

## Directory Structure

---

topics/ai_ml/
├── notebooks/
│   ├── linear_regression.ipynb
│   ├── kmeans_clustering.ipynb
├── notes/
│   ├── ai_for_everyone.md
├── ai_ml_basics.md

---
