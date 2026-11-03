
# 🩺 Data Cleanser: Advanced Healthcare Patient Records Preprocessing

A complete Data Science preprocessing project focused on cleaning noisy healthcare datasets, handling missing values using advanced imputation techniques, and detecting and treating outliers professionally.

---

## 🎯 Project Overview

Imagine working as a Data Analyst and receiving a raw healthcare dataset containing patient records such as **Age, BMI, Blood Pressure, Cholesterol, and Glucose Levels**.

Due to data entry errors, missing information, and unrealistic values, the dataset may contain several data quality issues.

**Data Cleanser** is designed to preprocess this raw healthcare data systematically and prepare a clean, structured dataset for Machine Learning applications, such as predicting `disease_risk`.

### Main Objectives

- Identify and handle missing values.
- Apply different imputation techniques.
- Detect outliers using statistical methods.
- Treat extreme values without deleting unnecessary records.
- Generate a final cleaned dataset.
- Prepare healthcare data for predictive modeling.

---

## 📂 Project Structure

The project is divided into three major parts:

### 1️⃣ Part A: Handling Missing Values

**Problem Identified:**

The raw dataset contained missing values in columns such as:

- `age`
- `bmi`
- `gender`
- `region`
- `cholesterol`
- `glucose`

**Techniques Applied:**

1. **Simple Imputer**
   - Median: Used for numerical columns.
   - Most Frequent (Mode): Used for categorical columns.

2. **KNN Imputer**
   - Identifies similar patient records.
   - Uses information from neighboring records to estimate missing numerical values.

3. **MICE Algorithm (Iterative Imputer)**
   - Estimates missing values through iterative regression.
   - Uses relationships between multiple numerical features.

**Outcome:** Missing values were handled using different imputation techniques while considering the relationships between patient health attributes.

---

### 2️⃣ Part B: Handling Outliers

**Problem Identified:**

The dataset contained extreme and potentially unrealistic values caused by synthetic data errors.

Examples included:

- Extremely high blood pressure values.
- Abnormal BMI values.
- Unusual cholesterol and glucose readings.

**Techniques Applied:**

1. **Z-Score Method**
   - Identifies observations that are far away from the mean.
   - Helps detect statistically unusual values.

2. **IQR (Interquartile Range) Method**
   - Detects outliers using the first quartile (Q1) and third quartile (Q3).
   - Identifies values outside the acceptable statistical range.

3. **Winsorization**
   - Applied percentile capping at the 1st and 99th percentiles.
   - Limits extreme values instead of deleting complete patient records.
   - Helps preserve the overall dataset size.

**Outcome:** Extreme values were treated while retaining patient records.

---

### 3️⃣ Part C: Final Clean Dataset & Delivery

After completing missing-value treatment and outlier handling:

- Combined all cleaned columns.
- Checked the final dataset for remaining missing values.
- Reviewed the processed numerical and categorical features.
- Exported the cleaned dataset into a new CSV file.

**Final Output File:**

`cleaned_patient_health_records.csv`

The generated dataset is prepared for further exploratory data analysis and Machine Learning preprocessing.

---

## 💡 Key Results & Learnings

| Category | Best Technique | Reason |
|---|---|---|
| Numerical Imputation | KNN / MICE | Considers relationships between numerical features. |
| Categorical Imputation | Mode | Fills missing values using the most frequent category. |
| Outlier Detection | Z-Score / IQR | Identifies statistically unusual observations. |
| Outlier Treatment | Winsorization | Caps extreme values instead of deleting records. |

### Key Learnings

- Understood different types of missing data problems.
- Learned how to apply Simple Imputer, KNN Imputer, and MICE.
- Explored statistical outlier detection methods.
- Understood the importance of Winsorization.
- Learned how to prepare healthcare datasets for Machine Learning.

**Important Note:** Data preprocessing can improve data quality, but it does not guarantee that a dataset is completely bias-free or suitable for clinical decision-making. Healthcare datasets require additional validation and domain expertise.

---

## 🛠️ Tools & Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming Language |
| Pandas | Data manipulation and analysis |
| NumPy | Numerical operations |
| Scikit-Learn | Imputation algorithms |
| SciPy | Statistical calculations and outlier treatment |

### Python Libraries

- `pandas`
- `numpy`
- `scikit-learn`
- `scipy`

---

## 🚀 How to Run This Project

Follow these steps to run the project on your local computer.

### Step 1: Clone the Repository

```bash
git clone <your-repository-url>
```

### Step 2: Navigate to the Project Folder

```bash
cd Data-Cleanser
```

### Step 3: Install Required Libraries

```bash
pip install pandas numpy scikit-learn scipy
```

### Step 4: Run the Project

Open the project in Jupyter Notebook or VS Code and execute the notebook cells sequentially.

---

## 📊 Final Output

The project generates a cleaned healthcare dataset:

```text
cleaned_patient_health_records.csv
```

This file can be used for:

- Exploratory Data Analysis (EDA).
- Data Visualization.
- Feature Engineering.
- Machine Learning Model Development.
- Predictive Healthcare Analytics.

---

## 🎓 Project Category

**Domain:** Data Science & Healthcare Analytics

**Project Type:** Data Preprocessing

**Level:** Advanced Beginner / Intermediate

**Primary Focus:** Missing Value Imputation, Outlier Detection, and Data Cleaning.

---

## 👩‍💻 Author

**Project:** Data Cleanser – Advanced Healthcare Patient Records Preprocessing

**Technologies:** Python, Pandas, NumPy, Scikit-Learn, SciPy
