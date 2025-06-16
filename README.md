#  Exploratory Data Analysis – Used Car Sales

**Author:** Mihika Sharma
**Date:** April 29, 2025
**Course:** BCA (Hons.) Data Science

## 📌 Project Overview
This project performs **Exploratory Data Analysis (EDA)** on a dataset of used car sales to:

* Assess data quality and completeness
* Discover patterns in vehicle types, pricing, and customer behavior
* Segment customers for marketing strategies
* Prepare the data for potential predictive modeling


## 📊 Dataset Summary

* **Records:** 10,000
* **Features:** 24 (e.g., Car Type, Engine Power, Price, Mileage, Sale Status, etc.)


## 🧹 Data Preprocessing

* **Null Handling:** Replaced missing numeric values with median or removed rows with too many nulls
* **Duplicates:** Removed duplicates to ensure data integrity
* **Date Conversion:** Converted 'Purchased Date' into datetime format for time-based analysis
* **Outlier Handling:** Removed/capped extreme values using IQR-based thresholds


## 📈 Statistical Overview

* **Average Price:** \$7,975

* **Mileage Mean:** 45,497 KM

* **Engine Power Mean:** 143 HP

* **Price Range:** \$6,000 – \$10,900

* **Mileage Range:** 1,000 – 99,983 KM

* **Power Range:** 100 – 250 HP

* **Skewness:**

  * Price & Mileage: Slight right-skew
  * Sold Price & Margin: Strong right-skew due to unsold entries and outliers


## 🔗 Correlations & Insights

* **Strong Positive Correlation:**

  * Purchased Price ↔ Sold Price (r ≈ 0.85)
* **Negative Correlation:**

  * Mileage ↔ Sold Price (r ≈ –0.45)
* **Weak Correlation:**

  * Engine Power has little impact on final price

## 🧠 Feature Engineering

Created new derived features:

* `PowerCategory`: Low, Mid, High
* `TotalMargin` & `ROI %`
* `CarAge`
* `PurchaseTime` components: year, month, day, hour, weekday, period

**Key Insight:**
Older cars tend to sell for less; high-powered vehicles yield better ROI.


## 📆 Time Series Analysis

* Data spans **Jan 2015 to Dec 2024**
* Sales dipped in 2020 (pandemic), then rebounded post-2021
* March and November see spikes due to seasonal demand
* Weekends show \~20% higher sales than weekdays


## 📊 Clustering & Segmentation

Used **Elbow Method** and RFM Segmentation:

* **Cluster 0:** Loyal Champions (High Value, Frequent, Recent)
* **Cluster 1:** At-Risk (Old customers, rare purchases)
* **Cluster 2:** Steady Buyers
* **Cluster 3:** One-Time Buyers

**Business Actions:**

* Reward loyal customers
* Re-engage at-risk users
* Cross-sell to steady buyers
* Offer promos to one-time buyers


## ⚠️ Anomaly Detection

* Detected pricing/mileage errors using **Z-score** and **Isolation Forest**
* Found extreme entries (e.g., \$0 cars, 200,000+ KM mileage)
* Recommended cleanup and fraud monitoring


## ✅ Conclusion

This EDA highlights critical insights into the used car sales business, offering data-driven suggestions for pricing, customer targeting, and sales optimization.

## 📌 Tools Used

* Python (pandas, matplotlib, seaborn, scikit-learn)
* Jupyter Notebook
* PowerPoint for reporting
