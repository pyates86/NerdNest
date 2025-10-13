# Python for AI

## Overview
Python is the backbone of AI development, powering libraries like NumPy, pandas, and scikit-learn. For SREs, Python enables scripting AI-driven tools, such as parsing Kubernetes logs or automating monitoring. This section focuses on mastering Python for AI tasks, with practical applications in cloud services.

## Learning Objectives
- Learn Python basics and AI-specific libraries (NumPy, pandas, scikit-learn).
- Write scripts for data manipulation and simple ML models.
- Apply Python to SRE tasks like log analysis or metric processing.

## Key Concepts
- **NumPy:** Fast array operations for numerical data (e.g., pod metrics).
- **Pandas:** Data manipulation with DataFrames, ideal for processing Kubernetes telemetry.
- **Scikit-learn:** Simple ML models for tasks like outlier detection.
- **SRE Application:** Use pandas to clean Prometheus data and scikit-learn to detect anomalies in Kubernetes clusters.

## Hands-On Exercises
1. **Data Preprocessing Script:**
   - **Task:** Clean a mock Kubernetes metrics dataset (e.g., remove nulls, normalize CPU usage).
   - **Tools:** Python, pandas, Jupyter Notebook.
   - **Code Example:**
     ```python
     import pandas as pd

     # Mock Kubernetes metrics
     data = pd.DataFrame({
         'pod_name': ['pod1', 'pod2', 'pod3', None],
         'cpu_usage': [0.5, None, 0.7, 0.9]
     })

     # Clean data
     data = data.dropna()
     data['cpu_usage_normalized'] = (data['cpu_usage'] - data['cpu_usage'].mean()) / data['cpu_usage'].std()
     print(data)
     ```
   - **Output:** Save as `preprocessing.ipynb`.
2. **Outlier Detection Script:**
   - Use scikit-learn’s Isolation Forest to detect outliers in pod metrics.
   - Save as `outlier_detection.py`.

## SRE Applications
- **Log Parsing:** Use pandas to process Kubernetes logs for AI-driven analysis.
- **Automation:** Script repetitive SRE tasks (e.g., generating alerts from metrics).
- **Monitoring:** Clean Prometheus data for ML model training.

## Resources
- **Free Course:** [Python for Data Science](https://www.datacamp.com/courses/intro-to-python-for-data-science) (DataCamp, 4 hours).
- **Tutorial:** [Pandas Documentation](https://pandas.pydata.org/docs/getting_started/intro_tutorials/).
- **Cheatsheet:** [NumPy Cheatsheet](https://www.datacamp.com/community/cheatsheets/numpy).
- **SRE-Specific:** “Python for DevOps” on O’Reilly (Chapter 3).

## Next Steps
- Complete the DataCamp Python course and commit notes to `notes/python_basics.md`.
- Commit the preprocessing notebook to `notebooks/preprocessing.ipynb`.
- Experiment with scikit-learn’s classification models for pod health checks.
- Share a script snippet on X with #Python #AIOps.

## Directory Structure

---

topics/ai_ml/
├── scripts/
│   ├── preprocessing.py
│   ├── outlier_detection.py
├── notebooks/
│   ├── preprocessing.ipynb
├── notes/
│   ├── python_basics.md
├── python_for_ai.md

---
