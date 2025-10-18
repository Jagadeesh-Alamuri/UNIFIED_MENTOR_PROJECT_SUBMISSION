# 📊 Data Science Project Portfolio Report

This document synthesizes the analysis and findings from four distinct data science and machine learning projects spanning Human Resources, Cybersecurity, Operations, and Finance.

***

## 1. Project: HR Employee Attrition Prediction

### 🎯 Objective
To build a predictive model to identify employees at high risk of turnover, thereby informing targeted retention strategies and managing human capital effectively.

### 🔍 Key Data Findings & EDA
* **Dataset:** HR Attrition data (1,470 records). Data was confirmed clean (no missing values or duplicates).
* **Critical Rate:** The overall employee Attrition Rate is **16.12\%**, highlighting a significant class imbalance in the target variable.
* **Demographics:** Mean employee age is approximately **36.9 years**.
* **Visuals:** Exploratory analysis included KDE plots of **Age** and bar plots of **Attrition Rate by Gender** to reveal specific patterns of turnover across demographic segments.

### 💻 Modeling & Recommendations
* **Preprocessing:** Used **StandardScaler** for numerical features (e.g., Monthly Income) and **One-Hot Encoding** for categorical features.
* **Models:** Employed a hybrid approach using the **Random Forest Classifier** and **Deep Learning Sequential Models** (Neural Networks).
* **Recommendation:** Prioritize intervention on factors identified as key attrition drivers, such as low Job Satisfaction or high Overtime usage.

***

## 2. Project: CloudWatch Web Attack Detection

### 🎯 Objective
To establish a robust machine learning pipeline for detecting anomalous and suspicious web traffic in CloudWatch logs, thereby enhancing cybersecurity monitoring.

### ⚙️ Data Preparation & Feature Engineering
* **Cleaning:** Time features were converted, and source IP Country Codes were standardized.
* **Feature Engineering:** Calculated the **`duration_seconds`** feature to measure traffic session length.
* **Scaling:** Applied **StandardScaler** to numerical traffic volume features (`bytes\_in`, `bytes\_out`).
* **Encoding:** Used **One-Hot Encoding** on categorical features for model input.

### 🧠 Modeling Approach
* **Anomaly Detection (Unsupervised):** Utilized the **Isolation Forest (IF)** algorithm, which is highly effective for flagging outliers that may represent zero-day or novel attacks.
* **Supervised Classification:** Implemented a **1D Convolutional Neural Network (CNN)** (using Conv1D layers) and a **Random Forest Classifier** for predicting specific attack types.
* **Conclusion:** The project successfully established a comprehensive, multi-model system ready for integration with live log streams.

***

## 3. Project: Incident Cause Analysis

### 🎯 Objective
To perform a descriptive analysis to quantify the relationship between **Cause category** and **Outcome of Incident**, supporting root cause analysis and safety improvements.

### 📈 Analytical Methodology
* **Grouping:** Incidents were grouped simultaneously by **Cause category** and **Outcome of Incident**.
* **Aggregation:** The total incident **Count** was summed for each unique cause-outcome pair.
* **Visualization:** Generated a **Stacked Bar Chart** to visually represent the distribution of outcomes across various cause categories.

### 💡 Actionable Insight
* The cross-analysis helps operational teams pinpoint which specific root causes are most correlated with the most **severe** or **high-cost outcomes**.
* This insight guides the prioritization of safety training, protocol updates, and resource allocation to target the highest-risk scenarios.

***

## 4. Project: Stock Market Trend Analysis

### 🎯 Objective
To analyze historical stock price data and use regression modeling to forecast trends, serving as the basis for a hypothetical trading strategy.

### ⚙️ Time-Series Setup & Modeling
* **Time-Series Setup:** The **Date** column was converted and set as the index.
* **Feature Engineering:** Engineered the **Daily Range** ($\texttt{High} - \texttt{Low}$) to measure intraday volatility.
* **Modeling:** Used **Linear Regression** for initial forecasting, evaluated using MSE and $R^2$ Score.

### 📉 Backtesting Results & Recommendations
* **Strategy Performance:**
    * **Total Strategy Return:** **-0.45**
    * **Total Market Return:** **-0.31**
* **Conclusion:** The implemented trading strategy **underperformed** the market benchmark during the test period.
* **Next Steps:** Incorporate advanced technical indicators (e.g., RSI, MACD) and explore time-series-specific models such as **ARIMA** or **Prophet** to improve performance.
