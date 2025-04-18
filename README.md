# 🛍️ Customer Segmentation in Retail

This project leverages transactional retail data to segment customers based on spending behavior and purchasing patterns. By using **PCA for dimensionality reduction** and **K-Means for clustering**, we identify distinct customer personas that businesses can target for tailored marketing strategies.
<div align="center">
  <img src="https://github.com/user-attachments/assets/2d0bc01d-6ec3-4e41-8f63-62f7775422f0" alt="Customer Segmentation Image" width="600"/>
</div>
---

## 📊 Dataset Overview

- **Source**: UCI Machine Learning Repository  
  [Online Retail Dataset](https://archive.ics.uci.edu/dataset/352/online+retail)
- **Records**: 541,909 transactions  
- **Duration**: 01-Dec-2010 to 09-Dec-2011  
- **Location**: UK-based online retailer  
- **Fields Used**: `Quantity`, `UnitPrice`, `CustomerID`

---

## 🧪 Technologies & Tools

- Python 🐍
- Pandas, NumPy
- Matplotlib, Seaborn
- Scikit-learn (PCA, KMeans)
- Google Colab

---

## 🧹 Data Cleaning & Preprocessing

- Removed irrelevant columns: `Country`, `Description`, `InvoiceDate`
- Dropped rows with missing `CustomerID`
- Engineered features:
  - `TotalSpend` = Quantity × UnitPrice
  - `TotalTransactions`
  - `AvgPurchaseValue`
- Removed customers with:
  - Negative/zero spend
  - Extreme outliers (capped at 99th percentile)
- Applied **log transformation** and **standardization** to reduce skewness and scale features for PCA.

---

## 🔍 Dimensionality Reduction (PCA)

- Reduced to 2 components:
  - **PC1**: Spending behavior
  - **PC2**: Purchase pattern
- Explained variance:  
  - **PC1**: 59.38%  
  - **PC2**: 40.34%  
  - **Total**: 99.72%

---

## 🤖 Customer Clustering (K-Means)

- Used **Elbow Method** to determine optimal K → **K = 3**
- Clustered customers into 3 segments using PCA-transformed data

### 📌 Cluster Profiles

| Cluster | PC1 Behavior       | PC2 Pattern        | Customer Type         | Business Strategy |
|--------:|--------------------|---------------------|------------------------|-------------------|
| 0       | High spending       | Stable buying       | **VIP Customers**      | Personalized offers, exclusive deals |
| 1       | Moderate spending   | Frequent purchases  | **Loyal Shoppers**     | Loyalty programs, bulk discounts |
| 2       | Low spending        | Occasional buying   | **Budget Customers**   | Promotions, engagement strategies |

---

## 📈 Visualizations

- Feature correlation heatmap
- PCA variance explained curve
- Elbow curve for optimal K
- 2D scatter plot of customer segments based on PCA components

---

## ✅ Conclusion

Through effective preprocessing, dimensionality reduction, and clustering:
- We successfully segmented over 4,300 customers
- Provided interpretable insights for customer targeting
- Demonstrated the power of combining PCA with clustering for real-world segmentation tasks

---

## 📂 Repository Structure

```
📁 Customer-Segmentation-Retail
├── 📄 README.md
├── 📊 Customer_Segmentation_Retail.ipynb
├── 📁 data/
│   └── online_retail.csv
├── 📁 images/
│   └── cluster_plot.png
│   └── elbow_curve.png
│   └── correlation_heatmap.png
└── 📁 models/
    └── kmeans_model.pkl
```

---

## 💡 Future Improvements

- Use **RFM (Recency, Frequency, Monetary)** analysis
- Apply **DBSCAN or Hierarchical Clustering** for comparison
- Deploy insights in a **streamlit dashboard**
