# 🛍️ RFM Analysis on Online Retail (UCI)

This project performs **RFM (Recency, Frequency, Monetary) analysis** on the UCI Online Retail dataset.  
It cleans the data, calculates RFM metrics, scores customers, segments them, and visualizes results with **matplotlib**.

---

## 🎯 Goal
- Load and clean the `OnlineRetail.csv` dataset  
- Compute **RFM metrics** for each customer  
- Assign **RFM scores (1–4)** and combine them into **RFM segments**  
- Create simple **customer segments** (e.g., Best, Loyal, At Risk)  
- Visualize customer distribution and segment-level RFM statistics  

---

## ⚡️ Workflow

### 1. Data Cleaning
- Remove missing `CustomerID` rows  
- Remove cancelled invoices (InvoiceNo starting with 'C')  
- Convert `InvoiceDate` to datetime  
- Create `TotalPrice = Quantity * UnitPrice`  

### 2. RFM Calculation
- **Recency**: Days since last purchase  
- **Frequency**: Number of purchases/invoices  
- **Monetary**: Total spent  

### 3. RFM Scoring
- Rank-based **quantile scores** 1–4  
  - Recency: lower is better  
  - Frequency & Monetary: higher is better  
- Combine scores into **RFM_Score** and **RFM_Segment**  

### 4. Customer Segmentation
- **Best Customers**: RFM_Score ≥ 9  
- **Loyal Customers**: RFM_Score ≥ 8  
- **Potential Loyalists**: RFM_Score ≥ 6  
- **At Risk**: RFM_Score ≥ 5  
- **Hibernating**: RFM_Score < 5  

### 5. Visualization
- Bar chart of **customer segment distribution**  
- Heatmap of **average R, F, M by segment**  

---

## 🛠 Tech Stack
- **Python**  
- **Pandas / NumPy** for data manipulation  
- **Matplotlib** for visualization  

---

## 📂 Dataset
Dataset: [UCI Online Retail](https://archive.ics.uci.edu/ml/datasets/online+retail)  
Expected CSV: `OnlineRetail.csv`  

---

## 📈 Outputs
- **RFM table** with scores & segments: `rfm_results.csv`  
- Segment distributions and RFM heatmaps as matplotlib charts  

---

## ⚠️ Notes
- RFM scoring uses **rank-based quantiles** to avoid edge issues on low-cardinality data  
- Customer segmentation thresholds are **tunable** based on business needs  

---

