# Data Analysis and Machine Learning Fundamentals

This repository serves as a comprehensive guide covering the foundational concepts of Data Analysis, Machine Learning, data acquisition, data cleaning, and Exploratory Data Analysis (EDA) with practical Python implementations.

## 📋 Table of Contents
- [Project Overview](#-project-overview)
- [Part A: Fundamentals of Data Analysis & Machine Learning](#-part-a-fundamentals-of-data-analysis--machine-learning)
- [Part B: Data Acquisition & Loading](#-part-b-data-acquisition--loading)
- [Part C: Data Understanding & Cleaning](#-part-c-data-understanding--cleaning)
- [Part D: Exploratory Data Analysis (EDA)](#-part-d-exploratory-data-analysis-eda)
- [Requirements & Installation](#-requirements--installation)

---

## 🎯 Project Overview
The primary objective of this project is to collect raw data, perform essential data cleaning, extract useful business insights, and prepare data for Machine Learning models. The code utilizes standard Python libraries such as Pandas, NumPy, Matplotlib, and Seaborn.

---

## 📌 Part A: Fundamentals of Data Analysis & Machine Learning

1. **What is Data Analysis?**
   - Data Analysis is the process of inspecting, cleaning, transforming, and modeling data to discover useful information, inform conclusions, and support decision-making.
   - **Key Steps:** Data Collection, Data Cleaning, Exploratory Data Analysis (EDA), and Data Interpretation.

2. **Data Science Project Lifecycle:**
   - **Business Understanding:** Define the target problem and project objectives.
   - **Data Acquisition:** Gather relevant data from diverse sources.
   - **Data Cleaning & Preprocessing:** Address missing values, duplicates, formatting issues, and outliers.
   - **EDA & Feature Engineering:** Analyze data patterns visually and create relevant features.
   - **Modeling & Evaluation:** Train machine learning algorithms and evaluate metrics.

3. **Machine Learning Problem Statement:**
   - **Title:** Customer Churn Prediction for a Subscription-Based Service.
   - **Problem Type:** Supervised Binary Classification (`Churn: 0 or 1`).
   - **Business Value:** Enables proactive identification of high-risk churn customers to optimize retention strategies and reduce customer loss.

4. **Tensors and NumPy Arrays:**
   - Conceptual breakdown and implementation of Scalars (0-D), Vectors (1-D), Matrices (2-D), and 3-D/N-D Tensors using NumPy.

---

## 📥 Part B: Data Acquisition

Methods for retrieving and loading datasets from different input sources:
- **CSV Files:** Loading structured tabular data using Pandas read methods.
- **JSON Files:** Parsing nested JSON records and transforming them into tabular formats.
- **SQL Databases:** Establishing connections with SQLite and executing standard SQL queries.
- **REST APIs:** Retrieving live web API data using the `requests` library and processing JSON responses.

---

## 🧹 Part C: Data Understanding & Cleaning

- **Initial Data Inspection:** Evaluating structural characteristics using `.info()`, summary statistics via `.describe()`, and null value counts.
- **Handling Missing Values:** Identifying missing data and applying imputation techniques (e.g., median imputation for `AnnualIncome`, mean imputation for `Age`).
- **Duplicate Removal:** Scanning and dropping duplicate records to guarantee data integrity.

---

## 📊 Part D: Exploratory Data Analysis (EDA)

- **Univariate Analysis:** Analyzing individual column distributions using histograms, count plots, and KDE plots (e.g., distributions of `Age` and `Annual Income`).
- **Bivariate & Multivariate Analysis:** Evaluating interactions between multiple variables using box plots, scatter plots, and correlation heatmaps (e.g., `Gender` vs. `Total Purchases`, `Annual Income` vs. `Churn Status`).

---

## 🛠️ Requirements & Installation

To run this notebook, ensure you have the required Python packages installed:

```bash
pip install pandas numpy matplotlib seaborn requests
