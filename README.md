# 📊 AI Sales Forecasting & Demand Intelligence

An end-to-end data analytics and machine learning project that analyzes historical sales data and forecasts future revenue using a Random Forest regression model.

## 🎯 Project Objective

The objective of this project is to:

- Analyze historical sales performance
- Identify revenue patterns across categories, regions and sales channels
- Engineer time-series features for forecasting
- Forecast daily revenue for January–June 2026
- Aggregate predictions into monthly revenue forecasts
- Classify future months into demand levels
- Present the results through an interactive Streamlit dashboard

## 📂 Dataset

The dataset contains 10,000 sales transactions covering:

**January 2023 – December 2025**

### Main Features

- Order_ID
- Customer_ID
- Order_Date
- Product
- Category
- Region
- Sales_Channel
- Payment_Method
- Quantity
- Unit_Price
- Discount
- Revenue

## 🔧 Data Preparation

The following preprocessing steps were performed:

1. Converted `Order_Date` into datetime format
2. Created a complete daily calendar
3. Aggregated transaction-level data into daily revenue
4. Filled missing calendar dates with zero revenue
5. Created calendar-based features
6. Created historical lag features
7. Created rolling average and rolling standard deviation features
8. Removed rows with insufficient historical information

## 🤖 Machine Learning Model

### Random Forest Regressor

The forecasting model uses:

- Calendar features
- Day and month information
- Year and quarter
- Day of week
- Weekend indicator
- Trend
- Historical revenue lags
- Rolling averages
- Rolling standard deviations

The final forecasting model was trained using historical daily revenue patterns.

## 📈 Model Evaluation

The model was evaluated using a chronological train-test split to preserve the time-series structure.

| Metric | Value |
|---|---:|
| MAE | ₹113,302 |
| RMSE | ₹140,187 |
| R² | -0.017 |

**Test Period:** June 2025 – December 2025

> Note: The reported metrics come from the evaluated daily Random Forest configuration used during model development. The final forecast is generated recursively using historical predictions and lag/rolling features.

## 🔮 2026 Revenue Forecast

The model generates a six-month forecast for:

**January 2026 – June 2026**

| Month | Forecast Revenue |
|---|---:|
| January 2026 | ₹7,380,859 |
| February 2026 | ₹7,518,693 |
| March 2026 | ₹8,443,455 |
| April 2026 | ₹8,211,982 |
| May 2026 | ₹8,446,499 |
| June 2026 | ₹8,242,505 |

### Forecast Summary

- **Total projected revenue:** ₹48.24M
- **Average monthly forecast:** ₹8.04M
- **Highest forecast:** May 2026
- **Forecast horizon:** 6 months

## 📊 Streamlit Dashboard

The interactive dashboard provides:

### Sales Overview
- Total Revenue
- Total Orders
- Units Sold
- Average Order Value

### Historical Analysis
- Monthly revenue trend
- Revenue by category
- Revenue by region
- Sales channel performance

### AI Forecasting
- Historical vs AI forecast
- Monthly revenue predictions
- Demand classification
- Forecast summary

### Business Intelligence
- Top-performing category
- Top-performing region
- Forecast outlook
- Business planning insights

## 🧠 Demand Classification

Forecasted revenue is compared with the historical average:

- **High Demand:** ≥ 110% of historical average
- **Medium Demand:** between 90% and 110%
- **Low Demand:** ≤ 90%

This classification can support inventory planning, sales planning and resource allocation.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Scikit-learn
- Plotly
- Streamlit
- Jupyter Notebook

## 📁 Project Structure

```text
AI_Sales_Forecasting/
│
├── app.py
├── README.md
├── requirements.txt
├── AI_Sales_Forecasting_10000_Rows.csv
├── AI_Sales_Monthly_Forecast_2026.csv
├── AI_Sales_Forecast_Jan_Jun_2026.csv
│
├── sales_forecasting.ipynb
│
├── data/
├── notebooks/
├── src/
└── venv/