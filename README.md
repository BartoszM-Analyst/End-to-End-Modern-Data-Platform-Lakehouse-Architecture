
# 🚀 End-to-End Sales Analytics Platform  
### From Raw Data to Executive Dashboard (Databricks + Delta Lake + Power BI)

---

## 📌 Project Overview

This project simulates a real-world enterprise scenario where a company lacks a centralized and standardized sales reporting system.

Sales data was stored in raw CSV exports without:

- unified KPI definitions  
- structured data modeling  
- return rate monitoring  
- product performance analysis  
- executive-level reporting  

To address this, I designed and implemented a modern Medallion Architecture analytics platform using Databricks and Delta Lake, delivering business-ready KPIs to an interactive Power BI dashboard.

---

## 🎯 Business Objective

The goal was to build an end-to-end analytics solution that:

- Centralizes raw sales data  
- Standardizes KPI calculations  
- Enables product and customer performance analysis  
- Tracks return rates and margin risks  
- Provides executive-level visibility through dashboards  

This project reflects how a scalable data platform can support data-driven decision-making.

---

## 🏗 Architecture

The solution follows the Medallion Architecture (Bronze → Silver → Gold) pattern.

Raw CSV Data  
↓  
Bronze Layer (Raw Ingestion - Delta Tables)  
↓  
Silver Layer (Data Cleaning, Joins, Transformations)  
↓  
Gold Layer (Business KPIs & Aggregations)  
↓  
Power BI Executive Dashboard  

### 🔹 Bronze Layer
- Raw data ingestion into Delta tables  
- Schema enforcement  
- Minimal transformations  
- Source-of-truth storage  

### 🔹 Silver Layer
- Data cleaning and validation  
- Business logic transformations  
- Joining fact and dimension data  
- Structured analytical model  

### 🔹 Gold Layer
- Business-ready aggregated tables  
- KPI calculations  
- Performance metrics  
- Optimized datasets for BI consumption  

---

## 🧱 Data Modeling

A star schema approach was implemented to ensure analytical performance and scalability.

### Fact Tables
- fact_sales
- fact_returns

### Dimension Tables
- dim_product
- dim_customer
- dim_category
- dim_date

This structure enables:

- Efficient slicing and filtering  
- Scalable BI reporting  
- Clear separation of business entities  
- Optimized aggregation performance  

---

## 📊 Implemented Business KPIs

### Revenue & Profitability
- Total Revenue  
- Gross Margin  
- Gross Margin %  
- Revenue by Category  
- Revenue Trends (Daily / Monthly)

### Product Performance
- Top Performing Products  
- Pareto Analysis (Top 20% Revenue Contributors)  
- Category Performance Ranking  

### Customer Insights
- Revenue by Customer  
- Customer Ranking  
- Customer Contribution Analysis  

### Returns Monitoring
- Return Rate  
- Product Return Risk  
- Category Return Analysis  

---

## 📈 Power BI Dashboard

The final layer of the project is an interactive executive dashboard built in Power BI.

The dashboard enables:

- Revenue trend analysis  
- Margin monitoring  
- Product performance insights  
- Return rate tracking  
- Drill-down capability by category and customer  

---

## ⚙️ Technology Stack

- Databricks  
- PySpark  
- Spark SQL  
- Delta Lake  
- Medallion Architecture  
- Star Schema Modeling  
- Power BI  

---

## 🔄 Scalability & Extensibility

The architecture is designed to support:

- Incremental data loading  
- Partitioned Delta tables  
- Streaming ingestion  
- Expansion to additional fact tables  
- Cloud deployment (Azure / AWS Databricks)  

---

## 💼 Business Impact Simulation

Although this is a portfolio project, it reflects a real enterprise scenario where:

- KPI definitions are standardized  
- Reporting time is reduced  
- Data silos are eliminated  
- Executive visibility is improved  
- Decision-making becomes data-driven  

---

## 🧠 Key Competencies Demonstrated

- End-to-end data platform design  
- Medallion Architecture implementation  
- Data modeling (Star Schema)  
- Business KPI definition  
- PySpark transformations  
- SQL aggregations  
- BI data preparation  
- Executive dashboard design  

---

## 📌 Why This Project Matters

This project demonstrates the ability to:

- Think beyond notebooks  
- Design scalable analytical systems  
- Translate business problems into technical solutions  
- Deliver clean, BI-ready datasets  
- Own the full analytics lifecycle  
