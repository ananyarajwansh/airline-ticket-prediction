# ✈️ Airline Ticket Price Prediction & Classification

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PowerBI](https://img.shields.io/badge/PowerBI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![XGBoost](https://img.shields.io/badge/XGBoost-1296DB?style=for-the-badge&logo=xgboost&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)

An end-to-end Machine Learning pipeline that solves two distinct problems using historical flight data:
1. **Regression**: Accurately predicting the exact numeric ticket price.
2. **Classification**: Categorizing the ticket price into 4 tiers (`Cheap`, `Moderate`, `Expensive`, `Very Expensive`).

---

## 📊 Project Lifecycle

The workflow of this project spans across the entire data science lifecycle:
1. **Data Analysis** (PowerBI)
2. **Preprocessing & Feature Engineering** (Pandas, SciPy)
3. **Modeling & Ensemble Learning** (Scikit-Learn, XGBoost, LightGBM)
4. **Testing & Validation**
5. **Web Deployment** (Flask, HTML, CSS, Bootstrap)

---

## 🛠️ Tech Stack

- **Data Science**: Python, NumPy, Pandas, DataPrep, SciPy, Matplotlib, Seaborn
- **Machine Learning**: Scikit-Learn, XGBoost, LightGBM, TensorFlow, Joblib
- **Business Intelligence**: Power BI
- **Web Deployment**: Flask, JavaScript, HTML, CSS, Bootstrap

---

## 🔍 Phase 1: Data Analysis & Preprocessing

### Analysis
Extensive Exploratory Data Analysis (EDA) was performed using Power BI to answer 20 core business questions regarding flight routes, timing, and pricing trends.

![Power BI Analysis Report](https://user-images.githubusercontent.com/76780379/170844979-5b42173d-e2a4-40fd-859a-5c16e60694c2.jpg)

### Preprocessing Pipeline
Because the dataset relies heavily on dates, the problem was treated as a **Time Series Forecasting** challenge:
1. **Time-Series Sorting**: Data was sorted (mergesort) by month, day, and time to prevent temporal data leakage during the train/validation split.
2. **Feature Engineering**: Extracted weekday, flight day, flight month, and calculated distances between source/destination.
3. **Outlier Detection**: Utilized Interquartile Range (IQR) on the target variable (Price).
4. **Data Transformation**: Applied Discrete Cosine Transform (DCT) to capture underlying periodic patterns in the flight schedule.
5. **Encoding**: Evaluated multiple categorical encoders, resulting in 3 distinct datasets for parallel training.

![Time Series Data](https://user-images.githubusercontent.com/76780379/170845001-c72271a3-f6b0-4886-bdf2-d2d2e7058622.jpg)

---

## 🧠 Phase 2: Modeling

Over 19 different algorithms were trained and evaluated across the Regression and Classification tasks.

### Regression (Exact Price Prediction)
10 models were evaluated, including XGBoost, LightGBM, Random Forest, and Decision Trees. 
- 🏆 **Best Performer**: A custom Bagging Ensemble (averaging HistGradientBoosting, LGBM, ExtraTrees, BaggingRegressor, and RandomForest) achieved an **R² score of 0.982**.
- 🥈 **Runner Up**: Random Forest Regressor (**R² score of 0.980**).

![Random Forest MSE](https://user-images.githubusercontent.com/76780379/172643425-76dfa607-f2ab-40cb-9249-55b336ab592d.jpg)

### Classification (Price Tier Prediction)
9 models were evaluated to classify tickets into 4 price tiers.
- 🏆 **Best Performer**: An Ensemble Stacking model combining Random Forest, Bagging Classifier, and Extra Trees Classifier.

---

## 🌐 Phase 3: Deployment

The final trained models were serialized (via `joblib`) and deployed through a lightweight web application.
- **Backend**: Python / Flask API
- **Frontend**: Responsive UI built with HTML, CSS, JavaScript, and Bootstrap.

---

## 👨‍💻 Author

**Ananya Raj Wansh**
- [GitHub](https://github.com/ananyarajwansh)
- [LinkedIn](https://www.linkedin.com/in/ananya-raj-wansh-758689293/)
