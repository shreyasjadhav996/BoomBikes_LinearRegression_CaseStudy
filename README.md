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
```
## ✅ Outcomes & Insights

- 🔍 **Year-over-year growth**: The `yr` variable (0 for 2018, 1 for 2019) showed a strong positive correlation with demand, indicating rising popularity of bike-sharing services.
- 🌡️ **Temperature** had a significant positive impact on bike rentals—warmer days tend to see higher usage.
- 💧 **Humidity** had a negative influence, with higher humidity leading to reduced rentals.
- ☁️ **Weather situation** and **season** played an important role, highlighting that demand varies across different times of the year and weather conditions.
- 📈 The model performs well in predicting bike demand and provides valuable insights that can be used to:
  - Optimize bike availability.
  - Plan marketing campaigns.
  - Strategize maintenance schedules.
  - Scale operations across new locations.

---

## 🛠️ Technologies Used

- **Python** – Core programming language for data analysis and modeling.
- **Pandas** – For data manipulation and transformation.
- **NumPy** – For numerical computations.
- **Matplotlib & Seaborn** – For data visualization and exploratory analysis.
- **scikit-learn** – For building and evaluating the regression model.
- **Jupyter Notebook** – For combining code, output, and documentation in one place.


