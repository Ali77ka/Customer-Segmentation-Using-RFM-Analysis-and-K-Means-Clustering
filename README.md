# 🧩 Customer Segmentation Using RFM Analysis and K-Means Clustering

## 1️⃣ Dataset
The dataset is from [Kaggle – Online Retail II (UCI)](https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci).  
It contains transactions from a **UK-based online retailer** during **2010–2011**.

---

## 2️⃣ Data Cleaning
Transactions with missing **Customer ID** values were removed,  
as RFM segmentation requires customer-level identification.

---

## 3️⃣ RFM Feature Engineering
For each customer, we calculated the three key RFM metrics:

| Metric | Description |
|:--|:--|
| **Recency (R)** | Days since the customer’s last purchase |
| **Frequency (F)** | Number of unique purchase invoices |
| **Monetary (M)** | Total money spent by the customer |

> *For readers already familiar with RFM: this recap is just to clarify the business meaning of each metric.*

---

## 4️⃣ Segmentation Approach
We considered two ways to segment customers:

1. **Manual segmentation** – ranking customers by R, F, and M values.
2. **Machine learning segmentation** – letting the algorithm discover natural clusters.

We chose **K-Means Clustering** for its simplicity and interpretability.

---

## 5️⃣ Scaling and Model Selection
To prepare the data for K-Means, we tested four scaling techniques:

- Min-Max Scaling  
- Standard Scaling  
- Robust Scaling  
- Logarithmic Transformation  

For each scaling method, we tested **k = 2 to 10** and evaluated the **Silhouette Score**.

✅ **Best setup:**  
`StandardScaler` + `k = 4` clusters

---

## 6️⃣ Cluster Interpretation & Business Actions

| Cluster | Description | Recommended Action |
|:--|:--|:--|
| **0** | Regular customers | Maintain engagement with personalized offers |
| **1** | Inactive customers (no recent purchases) | Send reactivation campaigns or win-back emails |
| **2** | VIP / High-value customers (very high M) | Offer loyalty rewards or exclusive promotions |
| **3** | Loyal customers (frequent buyers, moderate M) | Encourage referrals and strengthen brand loyalty |

---

## 7️⃣ Visualizations

To better understand and validate clusters, several visualizations were created:

| Visualization | Purpose |
|:--|:--|
| **📦 Box Plot** | Shows R, F, and M distributions per cluster; reveals variability and outliers |
| **🌐 3D Scatter Plot** | Visualizes clusters in RFM space to inspect separation and compactness |
| **🎯 PCA (2D)** | Reduces dimensionality for clearer cluster boundaries |
| **🔥 Heatmap** | Displays average RFM values per cluster for quick comparison |

---
---

## 🚀 Summary
This project demonstrates a complete **RFM-based customer segmentation pipeline** —  
from cleaning and feature engineering to clustering, evaluation, and visualization.

It helps businesses:
- Understand their customer base  
- Identify high-value or inactive segments  
- Design targeted, data-driven marketing strategies  

---

## 🧰 Tech Stack
- **Python** (pandas, scikit-learn, plotly)
- **Jupyter Notebook**
- **HTML reporting** (interactive visualizations)

---

### 📁 Output
The script generates:
- `rfm_report.html` — an interactive segmentation dashboard  
- Cluster summary table  
- PCA & 3D visualizations  
- Heatmap and box plots  

---

> *Author: Ali Karimi — Data for Growth*
