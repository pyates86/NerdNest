# Data Processing and Visualization

## Overview
Data processing and visualization are critical for preparing Kubernetes metrics for AI models. This section covers cleaning, transforming, and visualizing data using tools like matplotlib and seaborn, with a focus on SRE tasks like analyzing Prometheus metrics.

## Learning Objectives
- Clean and preprocess Kubernetes metrics for AI training.
- Visualize data to identify patterns (e.g., resource usage trends).
- Use matplotlib and seaborn for SRE dashboards.

## Key Concepts
- **Data Cleaning:** Handle missing values, outliers, and normalization.
- **Feature Engineering:** Create features like “average pod CPU” for ML models.
- **Visualization:** Plot time-series data (e.g., pod metrics) with matplotlib/seaborn.
- **SRE Application:** Visualize Kubernetes cluster health to train anomaly detection models.

## Hands-On Exercises
1. **Data Cleaning Notebook:**
   - **Task:** Clean a mock Prometheus dataset and visualize CPU trends.
   - **Tools:** Python, pandas, matplotlib.
   - **Code Example:**
     ```python
     import pandas as pd
     import matplotlib.pyplot as plt

     # Mock Prometheus data
     data = pd.DataFrame({
         'timestamp': pd.date_range('2025-10-01', periods=5, freq='H'),
         'cpu_usage': [0.5, 0.7, None, 0.9, 0.6]
     })

     # Clean and plot
     data = data.fillna(data['cpu_usage'].mean())
     plt.plot(data['timestamp'], data['cpu_usage'])
     plt.title('Pod CPU Usage')
     plt.savefig('cpu_usage.png')
     ```
   - **Output:** Save as `data_cleaning.ipynb`.
2. **Visualization Dashboard:**
   - Create a seaborn heatmap of pod resource correlations.
   - Save as `resource_heatmap.ipynb`.

## SRE Applications
- **Monitoring Dashboards:** Visualize Prometheus metrics for real-time cluster insights.
- **Model Training:** Clean data for AI models predicting resource needs.
- **Incident Analysis:** Plot anomalies to identify root causes in Kubernetes.

## Resources
- **Free Course:** [Data Visualization with Python](https://www.coursera.org/learn/python-for-data-visualization) (Coursera, 5 hours).
- **Tutorial:** [Seaborn Tutorial](https://seaborn.pydata.org/tutorial.html).
- **SRE-Specific:** “Visualizing Prometheus Metrics” on Grafana’s blog.

## Next Steps
- Complete the Coursera visualization course and commit notes to `notes/visualization.md`.
- Commit the cleaning notebook to `notebooks/data_cleaning.ipynb`.
- Integrate visualizations with Grafana for a K8s dashboard.
- Share a plot on X with #DataViz #SRE.

## Directory Structure

---

topics/ai_ml/
├── notebooks/
│   ├── data_cleaning.ipynb
│   ├── resource_heatmap.ipynb
├── images/
│   ├── cpu_usage.png
├── notes/
│   ├── visualization.md
├── data_processing_visualization.md

---
