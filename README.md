# ✈️ Flight Delay Classification (2015–2018)

This project aims to predict whether a flight will be **delayed (1)** or **on-time (0)** using historical flight data from 2015 to 2018. By building and evaluating various machine learning classifiers, the project provides actionable insights into patterns of flight delays and helps airlines make better scheduling decisions.

---

## 📌 Problem Statement

Flight delays lead to passenger dissatisfaction and significant financial losses for airlines. This project focuses on developing a predictive model to classify flights as delayed or not, based on features like departure/arrival times, delays, airline, distance, and more.

---

## 🎯 Objectives

- Analyze historical U.S. flight data to identify delay patterns.
- Clean, transform, and prepare the data for ML modeling.
- Build classification models such as Logistic Regression, Random Forest, Decision Tree, and SVM.
- Evaluate model performance using metrics like Accuracy, Precision, Recall, F1 Score, and ROC-AUC.

---

## 📁 Dataset

- Source: U.S. Department of Transportation (2015–2018)
- Size: ~24 million rows × 28 columns
- Major features:
  - `DEP_DELAY`, `ARR_DELAY`, `CARRIER_DELAY`, `TAXI_OUT`, `DISTANCE`
  - `OP_CARRIER`, `ORIGIN`, `DEST`, `CRS_DEP_TIME`, `ARR_TIME`, etc.

---

## ⚙️ Data Preprocessing

- Merged datasets from 2015–2018
- Removed irrelevant and high-missing-value columns
- Imputed delay-related missing values with 0
- Converted time features from HHMM to datetime
- Filtered to top 20 busiest airports (for dimensionality reduction)
- Transformed categorical columns using one-hot encoding
- Engineered new features (e.g., `WHEELS_OFF_elapse`, `DAYNAME`, `WEEKDAY`)
- Resolved multicollinearity using correlation analysis and feature importance from Random Forest

---

## 🔍 Target Variable

- **FLIGHT_STATUS**:  
  - `0` → On-time or early arrival  
  - `1` → Delayed (arrival delay > 15 minutes)

---

## 📊 Exploratory Data Analysis

- Distribution of flight delays
- Frequency of flights per carrier and per destination
- Weekly and monthly travel patterns
- Delay trends based on weekdays/weekends and city pairs

---

## 🧠 Models Used

| Model              | Accuracy | ROC-AUC | Precision | Recall | F1 Score |
|-------------------|----------|---------|-----------|--------|----------|
| Logistic Regression | 94.59%  | 0.979   | 89.91%    | 80.88% | 85.15%   |
| Random Forest       | 87.64%  | 0.957   | 97.54%    | 36.57% | 53.19%   |
| Decision Tree       | 93.38%  | 0.894   | 82.63%    | 82.95% | 82.79%   |
| SVM (fix needed)    | TBD     | TBD     | TBD       | TBD    | TBD      |

> ✅ Logistic Regression performed best overall in terms of balanced metrics.

---

## 📈 Feature Importance

Top predictive features:
- `DEP_DELAY`
- `WHEELS_OFF_elapse`
- `TAXI_OUT`
- `TAXI_IN`
- `ACTUAL_ELAPSED_TIME`
- Categorical encodings for airline, month, and weekday

---

## 🛠️ Tools & Libraries

- **Language**: Python 3.x
- **Libraries**:  
  `pandas`, `numpy`, `matplotlib`, `seaborn`,  
  `sklearn`, `feature_engine`, `datetime`, `calendar`

---

## 📦 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/flight-delay-classification.git
   cd flight-delay-classification
