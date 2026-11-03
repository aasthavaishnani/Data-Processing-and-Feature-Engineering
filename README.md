# 🚀 Holistic Data Preparer: End-to-End Data Preprocessing & Feature Engineering Pipeline

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-Data%20Analysis-orange)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-Preprocessing-yellow)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📌 Project Overview
The **Holistic Data Preparer** is an advanced, end-to-end data preparation and feature engineering project built for a fintech company. Real-world machine learning models fail when fed with raw, noisy, and unstructured data. This project simulates a complete production-grade data pipeline—taking messy data from diverse sources, cleaning it, handling missing values and extreme outliers, encoding categorical features, scaling numeric distributions, and engineering new predictive metrics to make the dataset **100% Machine Learning Ready**.

---

## 📊 Dataset Structure & Schema
The project utilizes a comprehensive **Customer Credit Risk Dataset** containing multi-type features:

| Field Name | Data Type | Description | Preprocessing Focus |
| :--- | :--- | :--- | :--- |
| `customer_id` | String / Int | Unique identifier for each customer | Primary Key |
| `age` | Integer | Age of customer (years) | Missing value imputation |
| `gender` | Categorical | Male / Female / Other | Category imbalance & encoding |
| `region` | Categorical | North / South / East / West | One-Hot Encoding |
| `education_level`| Ordinal Cat.| Primary / Secondary / Graduate / Post-Graduate | Ordinal Encoding |
| `employment_type`| Categorical | Salaried / Self-Employed / Unemployed | Categorical Imputation |
| `annual_income` | Float | Annual income (₹) | Outlier detection & Log Transform |
| `loan_amount` | Float | Loan amount requested (₹) | Outlier capping & Scaling |
| `loan_purpose` | Categorical | Home / Car / Education / Business / Other | One-Hot Encoding |
| `credit_score` | Float | Credit score (300–850) | Missing values & Binning |
| `repayment_history`| Integer | Number of missed payments in last 12 months | Numerical binning |
| `transaction_count`| Integer | Total transactions in last 6 months | Feature aggregation |
| `spending_ratio` | Float | Spending-to-Income ratio (%) | Mathematical transformations |
| `join_date` | Date | Date customer joined bank | Temporal feature extraction |
| `default_flag` | Binary Int | Target Variable (0 = No, 1 = Yes) | ML Model Target |

---

## 🛠️ Detailed Workflow & Implementation Phases

### 🔹 Part A: Conceptual Foundation
- Explored core concepts of data science project planning, problem framing (Binary Classification), and Tensor/NumPy multi-dimensional array operations.

### 🔹 Part B: Multi-Source Data Acquisition
- **CSV Files:** Loaded main transaction records.
- **JSON Files:** Parsed customer demographic metadata.
- **SQL Databases:** Extracted loan repayment history using SQLite relational queries.
- **External APIs:** Fetched external economic indicator metrics via HTTP requests.

### 🔹 Part C: Data Understanding & Cleaning
- Performed exploratory data analysis using `.info()` and `.describe()`.
- Handled missing values using **Simple Imputers** (Mean/Median for numerical, Most Frequent for categorical) and multivariate **KNN Imputers**.

### 🔹 Part D: Outlier Detection & Treatment
- Detected extreme income and loan anomalies using the **Interquartile Range (IQR)** method.
- Applied **Winsorization / Capping** to prevent extreme values from skewing the model.

### 🔹 Part E: Feature Engineering & Encoding
- **Temporal Extraction:** Extracted `join_year`, `join_month`, and `join_weekday` from `join_date`.
- **Ordinal Encoding:** Converted hierarchical education levels into ranked numerical values.
- **One-Hot Encoding:** Transformed nominal geographic regions and loan purposes into binary indicator columns.

### 🔹 Part F: Feature Scaling
- Standardized numeric features to zero mean and unit variance using **StandardScaler**.
- Applied **MinMax Scaling** to bound variables within a fixed $[0, 1]$ range.

### 🔹 Part G: Feature Construction & Transformations
- **Feature Construction:** Engineered domain-specific features like **Debt-to-Income Ratio** (`loan_amount / annual_income`).
- **Mathematical Transformations:** Applied logarithmic transformations (`np.log1p`) and square roots to normalize skewed financial distributions.

### 🔹 Part H: Final Deliverable & ML Readiness
- Compiled a comprehensive summary report confirming structural integrity, data consistency, and model readiness.

---

## 💻 Tech Stack & Dependencies
- **Programming Language:** Python 3.x
- **Data Manipulation:** Pandas, NumPy
- **Machine Learning & Preprocessing:** Scikit-Learn
- **Database Connectivity:** SQLite3
- **Environment:** Jupyter Notebook / Google Colab

---

## ⚙️ How to Run the Project Locally
1. Clone this repository:
   ```bash
   git clone [https://github.com/your-username/holistic-data-preparer.git](https://github.com/your-username/holistic-data-preparer.git)
