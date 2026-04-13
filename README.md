# B2B Sales Analytics Platform — Databricks · Delta Lake · Power BI

> **A company sitting on 12 months of raw sales exports had no reliable way to answer basic questions: Which products are actually profitable? What's the return rate by category? Who are the customers worth protecting?**  
> This platform was built to change that.

![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat-square&logo=databricks&logoColor=white)
![Delta Lake](https://img.shields.io/badge/Delta_Lake-00ADD8?style=flat-square)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat-square&logo=apachespark&logoColor=white)
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=flat-square&logo=powerbi&logoColor=black)
![Architecture](https://img.shields.io/badge/Architecture-Medallion-blueviolet?style=flat-square)

---

## The Problem

The business had sales data. It just wasn't usable.

Raw CSV exports, no standard KPI definitions, no return rate tracking, no way to slice performance by product category or customer tier. Every report was rebuilt from scratch each month. Every number was potentially wrong.

The core gaps:
- **No single source of truth** — different teams, different numbers
- **No return rate visibility** — losses were invisible until they hit margin
- **No product-level profitability** — revenue was tracked, margin wasn't
- **No scalable reporting layer** — every insight required manual effort

---

## The Solution

A modern **Medallion Architecture** data platform built on Databricks and Delta Lake, delivering clean, governed, BI-ready data to a Power BI executive dashboard.

```
Raw CSV exports
      │
      ▼
┌─────────────┐
│   BRONZE    │  Raw ingestion → Delta tables. Schema enforcement.
│             │  Immutable source of truth.
└──────┬──────┘
       │
       ▼
┌─────────────┐
│   SILVER    │  Cleaning, validation, joins, business logic.
│             │  Structured analytical model (Star Schema).
└──────┬──────┘
       │
       ▼
┌─────────────┐
│    GOLD     │  Aggregated KPIs, performance metrics.
│             │  Optimised for direct BI consumption.
└──────┬──────┘
       │
       ▼
  Power BI Dashboard — Executive reporting layer
```

---

## Data Model (Star Schema)

| Table | Type | Description |
|---|---|---|
| `fact_sales` | Fact | Transactional sales records |
| `fact_returns` | Fact | Return events with reason codes |
| `dim_product` | Dimension | Product attributes, category, pricing |
| `dim_customer` | Dimension | Customer segments, tiers |
| `dim_category` | Dimension | Category hierarchy |
| `dim_date` | Dimension | Full calendar table with fiscal periods |

---

## KPIs Delivered

### Revenue & Margin
- Total Revenue, Gross Margin, Gross Margin %
- Revenue trend by day / month
- Revenue by product category

### Product Performance
- Top revenue-generating SKUs
- **Pareto analysis** — which 20% of products drive 80% of revenue
- Category performance ranking

### Returns Intelligence
- **Return Rate by product and category** — identifying loss leaders
- Return trend over time
- High-risk product flagging

### Customer Analytics
- Revenue by customer, customer ranking
- Customer tier contribution analysis

---

## Power BI Dashboard

The Gold layer feeds directly into an interactive executive dashboard enabling:
- Revenue trend drill-down by period and category
- Gross margin monitoring with threshold alerts
- Return rate tracking with product-level detail
- Top customer and top product views side-by-side

---

## Why Medallion Architecture?

Most analytics projects dump everything into one notebook. Medallion separates concerns deliberately:

- **Bronze** is immutable — you can always reprocess from source
- **Silver** is your governed, clean layer — one definition of "clean customer" across the org
- **Gold** is optimised for speed — aggregations pre-built so dashboards don't timeout

This matters at scale. It also mirrors how modern data teams at companies like Zalando, Allegro, and ING actually structure their platforms.

---

## Tech Stack

| Layer | Technology |
|---|---|
| Compute & orchestration | Databricks |
| Storage format | Delta Lake |
| Transformation | PySpark, Spark SQL |
| Data modeling | Star Schema |
| Visualisation | Power BI |
| Architecture pattern | Medallion (Bronze / Silver / Gold) |

---

## Repository Structure

```
├── databricks/
│   ├── bronze/          # Raw ingestion notebooks
│   ├── silver/          # Cleaning & transformation logic
│   └── gold/            # KPI aggregation layer
├── data/                # Sample source files
└── powerbi/             # Dashboard file (.pbix)
```

---

## Scalability Notes

The platform is designed to extend without rebuilding:
- **Incremental loads** — Delta Lake handles upserts natively (MERGE)
- **Partitioned tables** — date-partitioned for query performance at scale
- **Cloud-ready** — architecture maps directly to Azure Databricks or AWS
- **New data sources** — additional Bronze tables slot in without touching Silver/Gold

---

*Built by Bartosz Majka · [LinkedIn](https://www.linkedin.com/in/bartosz-majka-a8088a35a/)*
