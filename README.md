# ML-Sales-Demand-Forecasting-Reorder-Recommendation-System
## 📌 Project Overview
This project implements a machine learning–based sales demand forecasting system combined with ERP-style reorder logic.  
It predicts future product demand using historical sales data and automatically recommends reorder quantities when stock falls below the reorder point.

---

## 🎯 Objectives
- Forecast daily product sales using machine learning
- Evaluate model performance using regression metrics
- Visualize actual vs predicted sales
- Generate reorder recommendations based on inventory logic

---

## 📂 Dataset Description
The project uses structured ERP-like datasets:

- **sales_orders.csv** – Historical sales transactions  
- **product_master.csv** – Product details  
- **stock_onhand.csv** – Current inventory levels  

---

## 🔄 Data Preprocessing
- Converted date columns to datetime format
- Removed invalid or zero sales entries
- Aggregated sales to daily product-level data
- Filled missing dates with zero sales to maintain time continuity

---

## 🛠 Feature Engineering
To convert time-series data into a supervised learning problem, the following features were created:

- `day_num` – Sequential day index  
- `lag_1` – Previous day sales  
- `lag_7` – Sales from 7 days ago  
- `rolling_mean_7` – 7-day moving average  

---

## ✂️ Train–Test Split
- Time-based split was used to avoid data leakage
- Last 30 days of data used as test set
- Remaining data used for training

---

## 🤖 Model Used
- **Linear Regression** (baseline regression model)

---

## 📊 Model Evaluation
Since this is a regression problem, the following metrics were used:

- **MAE (Mean Absolute Error):** 4.07  
- **RMSE (Root Mean Squared Error):** 6.36  
- **MAPE (Mean Absolute Percentage Error):** 36.86%

An **Actual vs Predicted Sales** plot was generated to visually validate model performance.

---
## 📦 Reorder Recommendation Logic
Reorder Point (ROP) is calculated using:
ROP = (Average Daily Demand × Lead Time) + Safety Stock

If current stock is below ROP, the system recommends a reorder quantity.

> Note: Stock values are simulated for demonstration purposes.

---

## 🖥 Streamlit Dashboard
A simple Streamlit interface allows users to:
- Select a product
- View average demand, current stock, and reorder point
- See reorder recommendations
- Visualize forecasted sales

---

## 🚀 Future Enhancements
- Add advanced models (Random Forest, XGBoost, LSTM)
- Include seasonality and holiday features
- Integrate with live ERP systems (Odoo)
- Improve inventory logic with dynamic lead time

---

## 🧠 Key Learning
This project demonstrates an end-to-end ML pipeline including data preprocessing, feature engineering, model training, evaluation, visualization, and business decision logic.

---

## 🔗 Technologies Used
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib
- Streamlit


