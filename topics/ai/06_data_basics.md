# Chapter 6: Data Basics for AI

In Software 1.0, the "logic" is the most important part of the application. In the world of AI (Software 2.0), **the Data is the logic**. A model is only as intelligent as the information it was fed during training. This chapter introduces the fundamentals of data handling that every engineer should know.

---

## 6.1 The Data Lifecycle
To build or use AI effectively, you need to understand how data moves through a system:
1. **Collection:** Gathering raw data (logs, database exports, API responses).
2. **Cleaning (Preprocessing):** Removing duplicates, handling missing values, and fixing formatting errors. This is where 80% of an AI engineer's time is spent.
3. **Exploration (EDA):** Using statistics and charts to find patterns or outliers.
4. **Splitting:** Dividing data into **Training** (for the model to learn) and **Testing** (to prove the model actually works).

---

## 6.2 Types of Machine Learning Data
Data is generally categorized by how it is labeled:

* **Structured Data:** Tabular data (like SQL tables or CSVs).
* **Unstructured Data:** Photos, audio files, and raw text (the bulk of Generative AI data).
* **Labeled Data:** Data that has a "target" or "answer" attached (e.g., a picture of a cat with a tag that says "cat").

---

## 6.3 Pandas: The Engineer's Spreadsheet
If you are working with data in Python, you are using **Pandas**. It is a library that allows you to treat data like a high-performance, programmable version of Excel.

**Key Concepts:**
* **DataFrame:** A 2D table structure (rows and columns).
* **Series:** A single column of data.
* **Filtering:** Selecting data based on conditions (e.g., `df[df['cpu_usage'] > 90]`).

---

## 6.4 Feature Engineering
Feature Engineering is the process of selecting and transforming raw data into "features" that make it easier for an AI to understand.
* **Example:** If you have a timestamp, the AI might struggle to see a pattern. If you convert that timestamp into a feature like `is_weekend` (True/False), the AI can more easily learn that traffic patterns change on Saturdays.

---

## 6.5 Garbage In, Garbage Out (GIGO)
This is the golden rule of AI. If your training data is biased, incomplete, or messy, your model will be biased, incomplete, or messy.
* **Bias Example:** If a tool meant to predict server failure is only trained on data from one specific data center, it will likely fail when deployed to a different environment with different hardware.

---

## 🛠 Hands-on: Playing with Data

For this exercise, we will use a small Python snippet to see how "DataFrames" work. You can run this in a local script or a Google Colab notebook.

```python
import pandas as pd

# 1. Create a tiny dataset of server logs
data = {
    'server_id': [101, 102, 103, 104, 105],
    'uptime_days': [45, 12, 150, 5, 80],
    'status': ['Online', 'Online', 'Down', 'Online', 'Online']
}

df = pd.DataFrame(data)

# 2. Filter for servers that have been up for more than 50 days
stable_servers = df[df['uptime_days'] > 50]

# 3. Print the results
print("Stable Servers:")
print(stable_servers)

# 4. Challenge: Add a new column called 'needs_reboot' 
# where uptime_days > 100.
```

---

> **Note:** Now that we understand the fuel (Data), Chapter 7 will show us the engine: **Introduction to Machine Learning**.
