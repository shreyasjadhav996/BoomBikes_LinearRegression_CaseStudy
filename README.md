# 🚲 Bike Sharing Demand Prediction

## 📌 Problem Statement

BoomBikes, a US-based bike-sharing provider, experienced a revenue dip during the COVID-19 pandemic. To recover post-lockdown and plan for the future, they aim to understand the key factors that influence the demand for shared bikes. The goal is to build a predictive model that can estimate daily bike rental counts, helping the company fine-tune their operations and marketing strategies.

## 🎯 Business Objective

- Identify significant variables influencing bike-sharing demand.
- Quantify how these variables impact the demand.
- Build a regression model using historical data to predict future demand (`cnt`).
- Provide insights to inform business strategy and expansion plans.

## 📁 Dataset Overview

The dataset contains daily observations of bike rentals across two years (2018 and 2019), along with features that capture:

- **Temporal variables**: season, month, weekday, year, etc.
- **Weather data**: temperature, humidity, wind speed, weather situation.
- **User types**: casual users, registered users.
- **Target variable**: `cnt` – total daily rentals (casual + registered).

**Note:** Certain numeric features like `season` and `weathersit` are categorical in nature and were appropriately encoded before modeling.

## 🔧 Data Preparation

Key preprocessing steps:

- Mapped numeric categorical variables (`season`, `weathersit`, etc.) to labeled strings.
- Verified that the `yr` column (0 for 2018, 1 for 2019) significantly contributes to the target due to increasing popularity of the service.
- Dropped `casual` and `registered` from the predictors to avoid data leakage, since their sum equals the target (`cnt`).
- Performed dummy encoding for categorical variables.

## 📊 Model Building

- **Model type**: Multiple Linear Regression
- **Target variable**: `cnt`
- **Evaluation metrics**: R-squared (on both train and test sets), residual analysis.

## 📈 Model Evaluation

After training and testing the model:

```python
from sklearn.metrics import r2_score
r2_score(y_test, y_pred)
