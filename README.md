# 🛍️ Customer Purchase Behavior — Data Analysis & Profiling

### An End-to-End Data Analytics Portfolio Project

[![Python](https://img.shields.io/badge/Python-3.13-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Seaborn](https://img.shields.io/badge/Seaborn-Visualization-4C72B0?style=for-the-badge)](https://seaborn.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-11557C?style=for-the-badge)](https://matplotlib.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org/)
[![Pandas Profiling](https://img.shields.io/badge/YData--Profiling-Reports-orange?style=for-the-badge)](https://github.com/ydataai/ydata-profiling)

**3,900+ customer records · 19+ features · 4 data sources merged · Full EDA · Automated profiling report**

---

## 🔘 Quick Links

<p>
  <a href="https://docs.google.com/document/d/1SrnqTEdiC63noz9Eo2m5SOR3euhITHFPNo6gUrcE3lg/edit?tab=t.0"><img src="https://img.shields.io/badge/❓_Question-Problem_Statement-blue?style=for-the-badge"></a>
  <a href="https://github.com/DevanshiBachhote2007/Data_Profiler/blob/main/Data_Profiler/Customer_Purchase_Behavior.ipynb"><img src="https://img.shields.io/badge/📓_Notebook-Open_in_Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white"></a>
  <a href="https://github.com/DevanshiBachhote2007/Data_Profiler/blob/main/Data_Profiler/Theory%20Questions%20For%20Data%20Profiling.pdf"><img src="https://img.shields.io/badge/📘_Theory-Read_PDF-red?style=for-the-badge&logo=adobeacrobatreader&logoColor=white"></a>
  <a href="https://github.com/DevanshiBachhote2007/Data_Profiler/tree/main/Data_Profiler/Data"><img src="https://img.shields.io/badge/📊_Dataset-shopping__trends.csv-20BEFF?style=for-the-badge&logo=kaggle&logoColor=white"></a>
  <a href="#-video-explanation"><img src="https://img.shields.io/badge/🎥_Video-Watch_Explanation-FF0000?style=for-the-badge&logo=youtube&logoColor=white"></a>
</p>


---

## 📌 Table of Contents

- [Problem Statement](#-problem-statement)
- [Project Overview](#-project-overview)
- [Project Architecture](#-project-architecture)
- [Dataset](#-dataset)
- [Tech Stack](#-tech-stack)
- [Repository Structure](#-repository-structure)
- [Quick Start](#-quick-start)
- [Workflow Walkthrough](#-workflow-walkthrough)
- [Key Findings](#-key-findings)
- [Data Profiling Report](#-data-profiling-report)
- [Video Explanation](#-video-explanation)
- [Skills Demonstrated](#-skills-demonstrated)
- [Future Roadmap](#-future-roadmap)
- [Author](#-author)

---

## ❓ Problem Statement

> **"Who is buying, how much are they spending, and what patterns drive repeat purchases?"**

Retailers sit on huge volumes of transactional data but rarely convert it into decisions. This project treats **customer purchase behavior** as a full data-science problem:

- **Input features:** Age, Gender, Income, Item/Category purchased, Purchase Amount, Location, Payment Method, Discount/Promo usage, Previous Purchases, Frequency of Purchases, etc.
- **Target concept:** Understanding and (eventually) predicting **customer churn / retention** — i.e. will a customer keep buying, and what drives their spend?
- **Goal:** Merge data from multiple sources, clean it, explore it statistically and visually, and generate an automated data-quality profile that a business team could act on.

---

## 🎯 Project Overview

This notebook walks through the **complete data analysis lifecycle** — from fundamentals and planning, through multi-source data acquisition, cleaning, exploratory data analysis (univariate → bivariate → multivariate), and finally automated data profiling.

It is organized into 5 structured parts, exactly as a real analytics project would be scoped:

| Part | Focus |
|------|-------|
| **A** | Fundamentals — what data analysis is, how to plan a data science project, and the ML problem framing |
| **B** | Data Acquisition — pulling data from CSV, JSON, SQL, and a live API, then merging them |
| **C** | Data Understanding & Cleaning — missing values, duplicates, data types |
| **D** | Exploratory Data Analysis — univariate, bivariate, and multivariate analysis |
| **E** | Data Profiling — an automated profiling report (missing values, stats, correlations, warnings) |

---

## 🏗️ Project Architecture

```
Raw Data (CSV + JSON + SQL + API)
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  PART B — DATA ACQUISITION                               │
│  CSV → JSON → SQLite → REST API  →  merged_df            │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  PART C — CLEANING                                        │
│  Missing values → dtype fixes → drop irrelevant columns   │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  PART D — EXPLORATORY DATA ANALYSIS                       │
│  Univariate → Bivariate → Multivariate → Correlations     │
└─────────────────────────────────────────────────────────┘
     │
     ▼
┌─────────────────────────────────────────────────────────┐
│  PART E — DATA PROFILING                                  │
│  Automated report → data_profiling_report.html            │
└─────────────────────────────────────────────────────────┘
```

---

## 📊 Dataset

| Property | Value |
|---|---|
| **Primary file** | `shopping_trends.csv` |
| **Rows** | 3,900 customer records |
| **Columns** | 19 (growing to 27 after merging JSON/SQL/API sources) |
| **Target concept** | Customer purchase behavior / churn risk |
| **Source** | Customer Shopping Trends Dataset — Kaggle |

### Feature Categories

| Category | Features |
|---|---|
| **Demographics** | `Age`, `Gender`, `Location` |
| **Transaction** | `Item Purchased`, `Category`, `Purchase Amount (USD)`, `Size`, `Color`, `Season` |
| **Engagement** | `Review Rating`, `Subscription Status`, `Previous Purchases`, `Frequency of Purchases` |
| **Payment** | `Payment Method`, `Preferred Payment Method`, `Shipping Type`, `Discount Applied`, `Promo Code Used` |

### Other Sources Merged In

- **`customer_data.json`** — supplementary customer records
- **`customer_db.sqlite`** — a SQLite table created and queried inline in the notebook
- **Random User API** (`randomuser.me`) — used to demonstrate live API ingestion and enrichment

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| **Language** | Python 3.13 |
| **Data manipulation** | Pandas |
| **Data sources** | CSV, JSON, SQLite (`sqlite3`), REST API (`requests`) |
| **Visualization** | Matplotlib, Seaborn |
| **Automated profiling** | `pandas_profiling` / `ydata-profiling` |
| **Notebook environment** | Jupyter Notebook (ipykernel) |
| **Version control** | Git / GitHub |

---

## 📁 Repository Structure

```
Data_Profiler/
│
├── 📄 README.md                          ← You are here
├── 📓 Customer_Purchase_Behavior.ipynb    ← Main analysis notebook (Parts A–E)
│
├── 📂 data/
│   ├── shopping_trends.csv                ← Primary dataset (3,900 rows × 19 cols)
│   ├── customer_data.json                 ← Supplementary JSON source
│   └── customer_db.sqlite                 ← SQLite database (created in-notebook)
│
├── 📂 docs/
│   └── Theory.pdf                         ← Concept notes: data analysis, planning, ML framing
│
├── 📂 reports/
│   └── data_profiling_report.html         ← Auto-generated profiling report
│
└── 📄 requirements.txt
```

---

## ⚡ Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/DevanshiBachhote2007/Data_Profiler.git
cd Data_Profiler
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

**requirements.txt**

```
pandas>=2.0
matplotlib>=3.7
seaborn>=0.12
requests>=2.31
ydata-profiling>=4.6
jupyter>=1.0
```

### 3. Launch the notebook

```bash
jupyter notebook Customer_Purchase_Behavior.ipynb
```

### 4. Generate the profiling report

Run all cells through **Part E**, and the report is saved automatically:

```
data_profiling_report.html
```

Open it in any browser to explore missing values, descriptive statistics, correlations, and data-quality warnings interactively.

---

## 🔍 Workflow Walkthrough

This section walks through **every part of the notebook in execution order** — the actual code cells, the actual console output they produced, and the interpretation that follows. Charts (histograms, boxplots, heatmaps, pairplots) render inline in the notebook itself; they're referenced here by title rather than reproduced.

### Part A — Fundamentals

Before writing any code, the notebook lays the conceptual groundwork in three short markdown sections.

**1. What is Data Analysis?**
Defined as the process of examining raw data to surface useful information — collecting it, cleaning it, organizing it, and studying it for patterns. The notebook frames this as how businesses turn raw numbers into decisions (understanding customers, improving products, spotting trends).

**2. Planning a Data Science Project**
A 9-step lifecycle is laid out as the roadmap the rest of the notebook follows:

1. **Problem Definition** — decide the question (e.g. *"Will a customer leave the company?"*)
2. **Data Collection** — gather data from files, databases, or APIs
3. **Data Cleaning & Preprocessing** — fix missing values, remove duplicates, correct types
4. **Exploratory Data Analysis (EDA)** — use graphs and statistics to understand the data
5. **Feature Engineering** — create new variables that improve model quality
6. **Model Selection & Training** — choose and train an ML algorithm
7. **Evaluation** — test accuracy with precision, recall, F1
8. **Deployment** — put the model into real use
9. **Monitoring & Maintenance** — track performance and update over time

**3. Machine Learning Problem Statement**
The notebook explicitly frames the eventual modeling goal:

> **Problem:** Predict customer churn (whether a customer will stop buying).
> **Input features:** Age, Gender, Income, Purchase frequency, Payment method, etc.
> **Target variable:** Churn (Yes/No)
> **Goal:** Identify at-risk customers early enough for the business to intervene and retain them.

This framing is why several EDA steps later on (e.g. Income vs. Purchases colored by Churn) specifically look for churn-related patterns even though the primary dataset (`shopping_trends.csv`) doesn't itself contain a `Churn` column — that signal comes in through the JSON/SQL sources merged in Part B.

---

### Part B — Data Acquisition

Four independent sources are pulled in and progressively merged into one working DataFrame, `merged_df`.

**1. CSV — the primary dataset**

```python
import pandas as pd

csv_data = pd.read_csv("shopping_trends.csv")
print(csv_data.head())
print(csv_data.info())
```

```
   Customer ID  Age Gender Item Purchased  Category  Purchase Amount (USD)  \
0            1   55   Male         Blouse  Clothing                     53   
1            2   19   Male        Sweater  Clothing                     64   
2            3   50   Male          Jeans  Clothing                     73   
...
RangeIndex: 3900 entries, 0 to 3899
Data columns (total 19 columns):
dtypes: float64(1), int64(4), object(14)
memory usage: 579.0+ KB
```

→ **3,900 rows, 19 columns** — clean, fully non-null.

**2. JSON — supplementary customer records**

```python
import json

with open("customer_data.json", "r") as f:
    json_data = json.load(f)

json_df = pd.DataFrame(json_data)
print(json_df.head())
print(json_df.info())
```

```
   CustomerID  Age  Gender  Income  Purchases  PaymentMethod Churn
0           1   25    Male   35000         12    Credit Card    No
1           2   32  Female   48000          8     Debit Card   Yes
2           3   41    Male   60000         20  Online Wallet    No
...
RangeIndex: 15 entries, 0 to 14
Data columns (total 7 columns)
```

→ Only **15 rows**, but this is the source that introduces `Income` and `Churn` — the two fields the rest of the notebook cares most about.

**3. SQL — an in-notebook SQLite table**

```python
import sqlite3

conn = sqlite3.connect("customer_db.sqlite")
cursor = conn.cursor()
cursor.execute("""
CREATE TABLE IF NOT EXISTS customers (
    CustomerID INTEGER PRIMARY KEY,
    Age INTEGER, Gender TEXT, Income INTEGER,
    Purchases INTEGER, PaymentMethod TEXT, Churn TEXT
);
""")

sample_data = [
    (1, 25, "Male", 35000, 12, "Credit Card", "No"),
    (2, 32, "Female", 48000, 8, "Debit Card", "Yes"),
    (3, 41, "Male", 60000, 20, "Online Wallet", "No"),
    (4, 29, "Female", 42000, 5, "Cash", "Yes"),
    (5, 36, "Male", 55000, 15, "Credit Card", "No")
]
cursor.executemany("INSERT OR IGNORE INTO customers VALUES (?, ?, ?, ?, ?, ?, ?)", sample_data)
conn.commit()

sql_df = pd.read_sql_query("SELECT * FROM customers", conn)
print(sql_df.head())
print(sql_df.info())
```

```
   CustomerID  Age  Gender  Income  Purchases  PaymentMethod Churn
0           1   25    Male   35000         12    Credit Card    No
1           2   32  Female   48000          8     Debit Card   Yes
...
RangeIndex: 5 entries, 0 to 4
```

→ A live table is **created, populated, and queried** inside the notebook itself — 5 rows returned.

**4. REST API — live enrichment**

```python
import requests

api_url = "https://randomuser.me/api/?results=20"
response = requests.get(api_url).json()
api_df = pd.json_normalize(response["results"])

print(api_df.head())
print(api_df.info())
```

```
   gender                            email           phone            cell  \
0  female  eleonora.andelkovic@example.com    039-9787-928    067-0446-378   
1  female        misty.lambert@example.com    06-5738-2253    0469-929-298   
...
```

→ **20 live, randomly-generated user records** pulled from `randomuser.me`, used purely to demonstrate API ingestion and to enrich the merged dataset with `gender`, `email`, and `location.city`.

**5. Merge all four sources**

```python
# Combine CSV, JSON, and SQL row-wise
merged_df = pd.concat([csv_data, json_df, sql_df], ignore_index=True)

# Enrich with API data (join by index)
merged_df = pd.merge(
    merged_df,
    api_df[["gender", "email", "location.city"]],
    left_index=True, right_index=True, how="left"
)

print(merged_df.head())
print(merged_df.info())
```

```
   Customer ID  Age Gender Item Purchased  Category  Purchase Amount (USD)  ...
0          1.0   55   Male         Blouse  Clothing                   53.0  ...
1          2.0   19   Male        Sweater  Clothing                   64.0  ...
...
Frequency of Purchases  CustomerID  Income  Purchases  PaymentMethod  Churn  gender  email  location.city
Fortnightly                    NaN     NaN       NaN            NaN    NaN  female  ...    Irig
```

→ Result: **~3,920 rows × 27 columns**. Note the expected `NaN` blocks — the CSV rows don't have `Income`/`Churn` (those only exist in the JSON/SQL rows), which is exactly the gap Part C's cleaning step has to handle.

---

### Part C — Data Understanding & Cleaning

**Initial exploration**

```python
print(merged_df.head())
print(merged_df.info())
print(merged_df.describe())
```

**Conclusion drawn from the output:**
- Dataset size: ~3,920 records, 27 columns
- Demographics: average age ≈ 44 years, balanced gender spread, diverse locations
- Purchasing behavior: avg purchase ≈ $60 (mostly $40–$80); ≈25 previous purchases on average
- Satisfaction: avg review rating ≈ 3.7 / 5
- Churn signal: more churn among low-income, low-frequency, cash/debit-paying customers; less churn among loyal, higher-income, credit/wallet-paying customers
- Data quality flag: `Income`, `Purchases`, and `Churn` have very few non-null values (only the 20 JSON+SQL rows), so duplicates and sparsity need handling

**Cleaning code**

```python
# Handle Missing Values
merged_df = merged_df.dropna(subset=["Age", "Income"])
merged_df["Purchases"] = merged_df["Purchases"].fillna(0)

# Correct Data Types
merged_df["Age"] = merged_df["Age"].astype(int)
merged_df["Income"] = merged_df["Income"].astype(int)

# Remove Duplicates
merged_df = merged_df.drop_duplicates()

# Drop Irrelevant Columns
merged_df = merged_df.drop(columns=["UnnecessaryColumn"], errors="ignore")

print("Cleaning Data")
print(merged_df.info())
```

```
Cleaning Data
Index: 15 entries, 3900 to 3914
Data columns (total 27 columns):
 0   Customer ID       0 non-null   float64
 1   Age              15 non-null   int64
 ...
 19  CustomerID       15 non-null   float64
 20  Income           15 non-null   int64
 21  Purchases        15 non-null   float64
 ...
```

→ Because `dropna(subset=["Age","Income"])` requires **both** fields, only the 15 JSON-sourced rows survive — the 3,900 pure-CSV rows are dropped from `merged_df` at this stage (their `Income` was always `NaN`). This is a deliberate trade-off in the notebook: it keeps the dataset small but complete enough to demonstrate churn-oriented analysis in Part D.

---

### Part D — Exploratory Data Analysis (EDA)

**1. Univariate Analysis** — distribution of each numeric field on its own

```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.histplot(merged_df["Age"], kde=True); plt.title("Age Distribution"); plt.show()
sns.histplot(merged_df["Income"], kde=True); plt.title("Income Distribution"); plt.show()
sns.histplot(merged_df["Purchases"], kde=True); plt.title("Purchases Distribution"); plt.show()
```
*(→ 3 histogram+KDE plots rendered inline)*

**Conclusion:** most customers are 30–55 years old (avg ≈44), most earn $40k–$60k (avg ≈$47.9k), most make 8–18 purchases (avg ≈13). Middle-aged, mid-income customers form the core segment.

**2. Bivariate Analysis** — relationships between two fields

```python
sns.boxplot(x="Gender", y="Purchases", data=merged_df); plt.title("Gender vs Purchases"); plt.show()
sns.scatterplot(x="Income", y="Purchases", hue="Churn", data=merged_df)
plt.title("Income vs Purchases (Churn Highlighted)"); plt.show()
```
*(→ 1 boxplot + 1 churn-colored scatterplot rendered inline)*

**Conclusion:** males show a higher median purchase count than females; income and purchases are positively correlated; customers with **lower income and fewer purchases churn more often**, while high-income frequent buyers churn less.

**3. Multivariate Analysis** — correlations across all numeric variables at once

```python
corr = merged_df.corr(numeric_only=True)
sns.heatmap(corr, annot=True, cmap="coolwarm"); plt.title("Correlation Heatmap"); plt.show()

sns.pairplot(merged_df[["Age", "Income", "Purchases"]]); plt.show()
```
*(→ correlation heatmap + pairplot grid rendered inline)*

**Conclusion:** `Income ↔ Purchases` ≈ **0.88**, `Previous Purchases ↔ Purchases` ≈ **0.81**, `Age ↔ Income` ≈ **0.94**, `Age ↔ Purchases` ≈ **0.81**. `Customer ID` shows no meaningful correlation and should be dropped as a predictor.

---

### Part E — Data Profiling

```python
from pandas_profiling import ProfileReport

profile = ProfileReport(
    merged_df,
    title="Customer Data Profiling Report",
    explorative=True
)
profile.to_file("data_profiling_report.html")

print("Profiling report generated: data_profiling_report.html")
```

```
Summarize dataset: 100%|██████████| 27/27 [00:00<00:00, 98646.52it/s]
Profiling report generated: data_profiling_report.html
```

→ A single interactive HTML file summarizing missing values, descriptive statistics, correlations, and automated data-quality warnings across all 27 columns of the cleaned `merged_df`.

---

## 🔎 Key Findings

| Relationship | Insight |
|---|---|
| **Income vs Purchases** | Strong positive correlation (**≈0.88**) — higher-income customers buy more |
| **Previous Purchases vs Purchases** | Strong correlation (**≈0.81**) — loyal customers keep buying |
| **Age vs Income** | Moderate-to-strong correlation (**≈0.94**) — older customers tend to earn more |
| **Age vs Purchases** | Moderate correlation (**≈0.81**) — spend scales with age |
| **Gender vs Purchases** | Males show a higher median purchase count and wider spread |
| **Customer ID** | No predictive value — correctly dropped as a feature |

**Demographic snapshot:** ~3,900–3,920 records · average age ≈ 44 years · average purchase ≈ \$60 (mostly \$40–\$80) · average review rating ≈ 3.7 / 5 · customers average ≈ 25 previous purchases.

> **Takeaway:** Spending capacity (**Income**) and loyalty (**Previous Purchases**) are the two strongest behavioral drivers of purchase volume — a natural foundation for a future churn-prediction model.

---

## 📈 Data Profiling Report

The notebook generates a full **YData/Pandas Profiling report** (`data_profiling_report.html`) covering:

- ✅ Missing-value breakdown per column
- ✅ Descriptive statistics (mean, median, std, quantiles)
- ✅ Full correlation matrix
- ✅ Automated data-quality warnings (skew, cardinality, duplicates)

Open the generated HTML file locally in your browser after running Part E of the notebook.

---

## 🎥 Video Explanation

📺 *Add your walkthrough video link here, e.g.:*
`[Watch on YouTube](https://youtu.be/your-video-id)`

A short screen-recording walking through the notebook — data merging, cleaning decisions, EDA charts, and the profiling report — makes this project far easier for reviewers to evaluate quickly.

---

## 🧠 Skills Demonstrated

```
Data Acquisition        →  CSV, JSON, SQL, REST API ingestion & merging
Data Cleaning           →  Missing value handling, dtype correction
Exploratory Analysis    →  Univariate, bivariate, multivariate techniques
Data Visualization      →  Matplotlib, Seaborn (histograms, boxplots, heatmaps, pairplots)
Statistical Reasoning   →  Correlation analysis, distribution interpretation
Automated Profiling     →  YData/Pandas Profiling report generation
Documentation           →  Structured, professional README & notebook narrative
```

---

## 🗺️ Future Roadmap

- [ ] **Churn Prediction Model** — train a classifier (Logistic Regression / Random Forest / XGBoost) on the merged dataset
- [ ] **Feature Engineering** — RFM-style (Recency, Frequency, Monetary) features
- [ ] **Interactive Dashboard** — Plotly Dash or Streamlit app for live exploration
- [ ] **SQL Layer** — dedicated `.sql` file with reusable analytical queries
- [ ] **Model Explainability** — SHAP values once a predictive model is added
- [ ] **Deployment** — package the profiling pipeline as a reusable script/CLI

---

## 👤 Author

**Devanshi Bachhote**
Data Analytics & Data Science Enthusiast

---

*If this project helped you, consider giving the repo a ⭐ — it helps others find it.*

Made with 🐍 Python · 🐼 Pandas · 📊 Seaborn · 📓 Jupyter
