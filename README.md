# 🚚 Delivery Time Prediction Project

## 📌 Overview
This project aims to predict delivery times for orders placed through **Porter**, a logistics and delivery platform. The primary objective is to build a regression model using order details, restaurant metadata, and delivery partner availability to improve operational efficiency and forecast delivery times accurately.

The project involves:
- Exploratory Data Analysis (EDA)
- Data Preprocessing and Feature Engineering
- Model Building with Random Forest and Recursive Feature Elimination (RFE)
- Theoretical discussions around Linear Regression

---

## 🎯 Objectives
- **Predict Delivery Time**: Build a regression model to estimate delivery durations.
- **Optimize Operations**: Enable better planning and logistics decisions.
- **Identify Key Factors**: Understand what influences delivery time the most.

---

## 🧾 Dataset
The dataset (`porter_data_1.csv`) contains the following features:

| Column | Description |
|--------|-------------|
| `market_id` | Market location ID |
| `created_at`, `actual_delivery_time` | Order placement and delivery timestamps |
| `store_primary_category` | Restaurant category |
| `order_protocol` | Order method (e.g., app, call) |
| `total_items`, `num_distinct_items` | Number and uniqueness of items |
| `subtotal`, `min_item_price`, `max_item_price` | Order value and item prices |
| `total_onshift_dashers`, `total_busy_dashers` | Dasher (delivery agent) availability |
| `total_outstanding_orders` | Pending orders |
| `distance` | Distance between restaurant and customer |

---

## 🔄 Data Pipeline

### ✅ Data Loading
- Load `porter_data_1.csv` using `pandas`.

### ⚙️ Preprocessing & Feature Engineering
- Convert timestamps to datetime objects.
- Encode categorical variables (`market_id`, `store_primary_category`, `order_protocol`).
- Create new features:
  - `time_taken` = Delivery time in minutes.
  - `order_hour`, `order_dayofweek`, `isWeekend` (binary).

### 📊 Exploratory Data Analysis (EDA)
- Histograms for numerical features.
- Count plots for categorical data.
- Scatter/boxplots for feature vs. `time_taken`.
- Correlation heatmaps.
- Outlier detection via IQR method.

### 🤖 Model Building
- Scale numeric features using `StandardScaler`.
- Build a **Random Forest** model with **RFE**.
- Evaluate with **MSE** and **RMSE**.

### 🔍 Model Inference
- Feature importance analysis.
- Residual plot analysis for assumptions: linearity, normality, etc.

---

## ⭐ Key Findings

### 🔝 Top Features
| Feature | Scaled Coefficient |
|---------|--------------------|
| `distance` | 0.2646 |
| `total_outstanding_orders` | 0.2606 |
| `total_onshift_dashers` | 0.2338 |

### 📈 EDA Insights
- Delivery time increases with `distance`, `total_busy_dashers`.
- Peak hours and weekends have higher delivery times.
- Order values are right-skewed due to complex or large orders.

### 📉 Model Performance
- Final Random Forest model (with 8 features) achieved **RMSE ≈ 2.57 minutes**.

---
