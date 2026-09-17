# 📊 Sales Analysis & Customer Segmentation

A data analytics and machine learning project that analyzes customer purchasing behavior and segments customers using **RFM Analysis** and **K-Means Clustering**.

The project processes sales transaction data, calculates **Recency, Frequency, and Monetary (RFM)** metrics, scales the features, and applies K-Means clustering to identify different customer groups.

---

## 🚀 Project Overview

Understanding customer purchasing behavior is important for businesses to improve marketing strategies and customer retention.

This project uses historical sales transaction data to:

* 🧹 Clean and preprocess sales data
* 💰 Calculate total transaction amounts
* 👥 Analyze individual customer purchasing behavior
* 📈 Perform RFM analysis
* 📊 Standardize RFM features
* 🤖 Apply K-Means clustering
* 📉 Use the Elbow Method to analyze cluster selection
* 📏 Evaluate clustering using Silhouette Score
* 📐 Evaluate clustering using Davies-Bouldin Index
* 📊 Visualize customer clusters
* 🔍 Generate cluster-level summaries

---

## 🧠 Methodology

### 1. Data Loading

The project loads the sales dataset using Pandas.

```python
import pandas as pd

df = pd.read_excel("sales2.xlsx")
```

### 2. Data Cleaning

The dataset is cleaned by:

* Removing records without a Customer ID
* Removing cancelled invoices
* Removing transactions with invalid quantities
* Removing transactions with invalid prices
* Removing duplicate records

```python
df = df.dropna(subset=["Customer ID"])

df = df[~df["Invoice"].astype(str).str.startswith("C")]

df = df[(df["Quantity"] > 0) & (df["Price"] > 0)]

df = df.drop_duplicates()
```

### 3. Tot
