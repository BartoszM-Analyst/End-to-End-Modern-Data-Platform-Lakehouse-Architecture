# Enterprise Sales Analytics Platform  
**End-to-End Data Analytics Project (Databricks • PySpark • Delta Lake • Power BI ready)**

---

## 📌 Project Overview

This project presents a **full analytical data pipeline** built according to **modern data engineering and analytics best practices**:

**Bronze → Silver → Gold architecture**, designed to handle **dirty, multi-source enterprise data** and transform it into **business-ready analytical models**.

The goal of the project is not only to analyze sales, but to **demonstrate real-world analytical thinking**, data quality awareness, and KPI correctness.

---

## 🧱 Architecture

Raw CSV Files
↓
Bronze Layer (Databricks)

raw ingestion

schema inference

source metadata

no data cleaning

↓
Silver Layer

data cleansing

safe casting (try_cast)

business rules

deduplication

validated relationships

↓
Gold Layer

business KPIs

aggregation

Pareto analysis

Power BI ready tables


---

## 🥉 Bronze Layer — Raw Ingestion

**Purpose:**  
Store raw data exactly as received from multiple source systems.

**Key characteristics:**
- no transformations
- intentionally dirty data
- schema drift tolerated
- ingestion metadata added

**Data sources:**
- sales
- products
- customers
- returns

---

## 🥈 Silver Layer — Data Cleaning & Validation

**Purpose:**  
Transform raw data into **clean, consistent, analytics-ready datasets**.

### Key transformations:
- removal of invalid business keys
- trimming string columns
- safe type casting (`try_cast`)
- handling nulls and malformed values
- deduplication
- enforcing business logic (e.g. positive quantities and prices)

### Silver tables:
- `silver_sales`
- `silver_products`
- `silver_customers`
- `silver_returns`

---

## 🥇 Gold Layer — Business Analytics

**Purpose:**  
Deliver **stable, trusted analytical tables** optimized for BI tools.

### Gold tables include:

#### 📊 Sales KPIs
- `gold_sales_summary`
  - revenue over time
  - order count
  - units sold

#### 🧠 Product Analytics
- `gold_product_performance`
- `gold_product_return_rate`

#### 🧠 Category Analytics
- `gold_category_performance`
- `gold_category_return_rate`

#### 👥 Customer Analytics
- `gold_customer_revenue_pareto`
  - revenue concentration (80/20 rule)
- `gold_customer_business_metrics`
  - AOV
  - return rate
  - customer quality indicators

#### 🔁 Quality KPI
- `gold_returns_kpi`
  - return rate calculated **only on valid sales orders**
  - avoids inflated or logically incorrect metrics

---

## 🧠 Key Analytical Decisions

- Return rates are calculated **only on the intersection of sales and returns**
- Dirty data is expected and handled explicitly
- Strategic KPIs (Pareto) are separated from operational KPIs (quality metrics)
- Tables are designed to **minimize joins in Power BI**

---

## 📊 Power BI Usage

Gold tables are designed to be **plug-and-play** in Power BI:

Recommended dashboards:
- Executive sales overview
- Product & category Pareto (80/20)
- Customer segmentation
- Return rate quality monitoring
- Revenue vs returns analysis

---

## 🛠️ Technologies Used

- Databricks
- PySpark
- Delta Lake
- SQL
- Git / GitHub
- Power BI (consumption layer)

---

## 🎯 Why This Project Matters

This project demonstrates:
- real-world data modeling
- analytical maturity
- business-oriented KPI design
- ability to detect and fix logical inconsistencies
- readiness for mid+/senior analytics roles

---

## 📎 Author

**Bartosz Majka**  
Data Analyst / Analytics Engineer  

