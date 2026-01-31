# ⏱📊 Time Series Forecasting with Machine Learning

This project focuses on forecasting **hourly taxi demand** using historical data while strictly respecting the time dimension to prevent data leakage and ensure realistic model evaluation.

---

## 🏷️ Tech Stack
Python · pandas · NumPy · scikit-learn · Matplotlib · Jupyter Notebook

---

## 📑 Table of Contents
1. 🎯 Problem Statement  
2. 🎯 Project Goals  
3. 🧾 Dataset Overview  
4. 🧠 Approach & Methodology  
5. 📊 Evaluation & Metrics  
6. 🧰 Tools & Libraries  
7. ▶️ How to Run the Project  
8. 📁 Project Structure  
9. 💡 Key Takeaways  
10. 🚀 Next Steps & Improvements  
11. 👤 Author & Connect  

---

## 🎯 01 — Problem Statement
Accurately forecast future values in time-dependent data while preserving chronological order and avoiding data leakage that could inflate model performance.

---

## 🎯 02 — Project Goals
- Identify temporal patterns and seasonality in hourly taxi demand  
- Engineer time-based features such as lag values and rolling statistics  
- Train and evaluate forecasting models using time-aware validation  
- Compare model performance against a naive baseline  

---

## 🧾 03 — Dataset Overview
- Hourly time-indexed observations  
- Target variable: `num_orders`  
- Data resampled to hourly frequency  
- Chronological ordering preserved throughout the analysis  

A small sample dataset is included in `data/sample/` to allow the project to run without access to the full dataset.

---

## 🧠 04 — Approach & Methodology
This project follows a leakage-free time series workflow:

**Exploratory Data Analysis (EDA)**
- Visualized hourly demand to identify trends and seasonality  

**Feature Engineering**
- Lag features for the previous 1–24 hours  
- Rolling mean features using 3, 6, 12, and 24-hour windows  
- Calendar features including hour of day and day of week  

**Train/Test Split**
- Time-based split without shuffling  
- Ensures future data is never used to predict the past  

---

## 📊 05 — Evaluation & Metrics
Models were evaluated using **Root Mean Squared Error (RMSE)**.

| Model | RMSE |
|------|------|
| Baseline (lag-1) | ~29.29 |
| Linear Regression | ~20.45 |
| Random Forest | ~20.68 |

Linear Regression achieved the lowest RMSE, significantly outperforming the baseline model and demonstrating the impact of feature engineering on short-term forecasting.

---

## 🧰 06 — Tools & Libraries
- Python  
- pandas  
- NumPy  
-  -learn  
- Matplotlib  

---

## ▶️ 07 — How to Run the Project
1. Open `Sprint13_Time_Series.ipynb`
2. Run all cells from top to bottom  
3. Ensure the sample dataset exists at:

---

## 📁 08 — Project Structure
Sprint13_Time_Series/
│
├── data/
│ └── sample/
│ └── taxi_sample.csv
│
├── Sprint13_Time_Series.ipynb
├── README.md
└── .gitignore


---

## 💡 09 — Key Takeaways
- Time-aware validation is critical for forecasting tasks  
- Simple models can outperform complex ones with strong feature engineering  
- Baseline models provide essential context for evaluating performance  
- Model selection should balance accuracy, interpretability, and practicality  

---

## 🚀 10 — Next Steps & Improvements
- Hyperparameter tuning for tree-based models  
- Feature selection to reduce multicollinearity  
- Evaluation on longer forecasting horizons  
- Production-style inference and monitoring  

---

## 👤 11 — Author & Connect
**Tamauri Olive**  
Aspiring Wellness Data Scientist — blending AI, empathy, and impact  

🔗 LinkedIn: www.linkedin.com/in/tamauri-olive-499845113  
🔗 GitHub: https://github.com/Olivenatural
