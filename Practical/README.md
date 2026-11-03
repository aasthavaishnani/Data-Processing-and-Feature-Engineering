# Comprehensive Technical Project Report
## Project Title: “Customer Purchase Propensity - Data Cleaning and Feature Engineering Pipeline”

---

### 1. Executive Summary & Problem Framing
In modern data-driven e-commerce ecosystems, identifying customer purchase intent prior to conversion is critical for targeted marketing campaigns, resource allocation, and revenue optimization. As a Junior Data Analyst, the primary mandate of this project is to construct a rigorous, production-grade data preprocessing and feature engineering pipeline. Raw operational data is inherently heterogeneous, messy, and incomplete—featuring missing values, extreme outliers, unstructured datetime strings, and unscaled distributions. 

This project systematically transforms raw multi-source logs into a pristine, machine-learning-ready dataset through a structured 10-step pipeline. The problem is framed as a **Binary Classification** task where the target variable, `purchased` ($y \in \{0, 1\}$), represents customer conversion based on demographics, historical transaction velocity, and product metadata.

---

### 2. Multi-Source Data Integration Architecture
Real-world data ingestion requires unifying disparate storage paradigms. The dataset was synthesized and pulled from four independent operational channels:

| Source Type | File / Endpoint | Description & Attributes |
| :--- | :--- | :--- |
| **Structured CSV** | `customers.csv` | Customer demographics including `customer_id`, `age`, `income`, `education`, and `signup_date`. |
| **JSON Logs** | `transactions.json` | Behavioral records containing `total_purchases`, `last_purchase_date`, and target column `purchased`. |
| **SQL Database** | `products.sql` (SQLite) | Relational product catalog mapping `product_id` to product `category` and `price`. |
| **REST API** | `DummyJSON Users` | External telemetry providing supplementary user attributes (`gender`, `bloodGroup`). |

These sources were integrated using relational inner and left joins on composite keys (`customer_id`, `product_id`), establishing a unified analytical schema.

---

### 3. Detailed 10-Step Pipeline Methodology

#### Step 1: Project Planning & Problem Framing
* Established the project lifecycle scope, defining data analysis objectives, preprocessing dependencies, and framing the predictive target as a binary classification problem.

#### Step 2: Data Import, Integration & Initial Exploration
* Executed multi-format ingestion using `pandas`, `sqlite3`, and `requests`. Validated structural integrity using `.info()`, `.describe()`, and `.head()` methods to identify preliminary data anomalies.

#### Step 3: Exploratory Data Analysis (EDA)
* **Univariate Analysis:** Analyzed individual numerical columns via histograms and KDE plots to detect skewness.
* **Bivariate Analysis:** Evaluated feature-to-target correlations (e.g., income tiers vs. purchase conversion).
* **Multivariate Analysis:** Constructed correlation heatmaps to check for multicollinearity among continuous predictors.

#### Step 4: Missing Data Imputation Strategy
* **Categorical Missingness:** Imputed missing values in `education` using **Most Frequent (Mode) Imputation**.
* **Numerical Missingness:** Applied **Median SimpleImputer** on `age` to avoid mean distortion.
* **Multivariate Imputation:** Deployed **KNN Imputer ($k=3$)** on `income`, leveraging local neighborhood feature similarities to retain variance.

#### Step 5: Outlier Detection & Treatment
* Identified an extreme income anomaly ($1,500,000) using the **Interquartile Range (IQR)** method:
  $$\text{IQR} = Q_3 - Q_1, \quad \text{Bounds} = [Q_1 - 1.5 \times \text{IQR}, Q_3 + 1.5 \times \text{IQR}]$$
* Applied **Winsorization / Percentile Capping (5th and 95th percentiles)** via `np.clip` to neutralize outlier distortion without dropping valuable data rows.

#### Step 6: Handling Mixed & Date/Time Variables
* Converted raw string date columns (`signup_date`, `last_purchase_date`) to pandas datetime objects.
* Engineered temporal features: `days_since_signup` and `days_since_last_purchase` (with missing purchase dates imputed to a sentinel value of `999`).
* Parsed mixed alphanumeric customer IDs (`CUST_101`) to extract pure numerical identifiers (`customer_id_num`).

#### Step 7: Categorical Encoding & Numerical Binning
* **Ordinal Encoding:** Mapped hierarchical educational tiers (`High School` < `Bachelor` < `Master` < `PhD`) using `OrdinalEncoder`.
* **One-Hot Encoding:** Converted nominal product categories into binary indicator columns via `pd.get_dummies`.
* **Numerical Binning:** Discretized continuous income values into behavioral categories (`Low`, `Medium`, `High`) using `pd.cut`.

#### Step 8: Feature Scaling via ColumnTransformer
* Deployed `ColumnTransformer` to apply specialized scalers simultaneously:
  * **StandardScaler:** Applied to `age` (centers mean to 0, variance to 1).
  * **MinMaxScaler:** Applied to `total_purchases` (rescales to range $[0, 1]$).
  * **RobustScaler:** Applied to `income` (utilizes median and IQR for outlier resilience).

#### Step 9: Feature Construction & Mathematical Transformations
* **Interaction Features:** Created purchase velocity metrics:
  $$\text{purchases\per\day} = \frac{\text{total\purchases}}{\text{days\since\signup} + 1}$$
* **Mathematical Transforms:** Applied Log transformation (`np.log1p`) and **Yeo-Johnson PowerTransformer** to normalize skewed distributions.
* **Binarization:** Converted purchase frequency into a binary `frequent_buyer` indicator threshold.

#### Step 10: Final Export & Summary Report
* Exported the fully cleaned, transformed, and feature-engineered dataset to `processed_customer_data.csv`, complete with reproducible Python code and repository documentation.

---

### 4. Technical Performance & Key Findings
* **Imputation Efficiency:** `KNNImputer` outperformed basic mean imputation by preserving local demographic correlations.
* **Robustness:** `RobustScaler` combined with percentile capping ensured that income skewness did not destabilize downstream model gradients.
* **Model Readiness:** The resulting dataset provides clean numerical arrays, properly encoded categorical matrices, and engineered interaction metrics fully optimized for tree-based or linear classification models.
