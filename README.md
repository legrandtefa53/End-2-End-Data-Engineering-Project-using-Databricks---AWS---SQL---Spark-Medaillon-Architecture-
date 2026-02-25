# **End‑to‑End Data Engineering Project using Databricks, AWS, SQL, Spark & the Medallion Architecture**

This project walks through building a complete **end‑to‑end data engineering pipeline** using **Databricks Free Edition**, **AWS S3**, **PySpark**, **SQL**, and the **Medallion Architecture** (Bronze → Silver → Gold).  
The use case is based on the **FMCG (Fast‑Moving Consumer Goods)** domain, where two companies merge and need a unified analytics layer.

The project covers ingestion, cleaning, transformation, modeling, and dashboard creation using **Databricks’ Genie AI assistant**.

<p align="center">
  <img width="500" height="200" alt="image" src="https://github.com/user-attachments/assets/5031480e-9fda-4938-8c3f-b4c2fe836f99" />
</p>

---

## 🚀 **Project Overview**

A parent FMCG company (**Atlon**) acquires a smaller company (**SportsBar**).  
```
The matter : They don't have a proper Data Engineering system. 
```
Therefore, the goal is to build a **clean, unified, scalable data platform** for both companies. The tech stack data engineering project is :

- Databricks 
- AWS S3
- Python
- Spark & SQL
- Delta Lake
- Medallion Architecture
- BI Dashboard & Databricks AI (Genie)

---

## 🧱 **Architecture**

### **High‑Level Architecture**
```
AWS S3  →  Databricks Bronze  →  Silver  →  Gold  →  Power BI / Dashboard
```

### **Medallion Layers**
| Layer | Purpose |
|-------|---------|
| **Bronze** | Raw ingestion from S3 (CSV files, full + incremental loads) |
| **Silver** | Data cleaning, standardization, deduplication |
| **Gold** | Business-ready tables, harmonized schema, star model |

---

## 📂 **Project Structure**

```
├── notebooks/
│   ├── 01_bronze_ingestion.ipynb
│   ├── 02_silver_cleaning.ipynb
│   ├── 03_gold_modeling.ipynb
│   ├── 04_dashboard_prep.ipynb
│
├── data/
│   ├── parent_company/
│   ├── child_company/
│       ├── full_load/
│       ├── incremental_load/
│
├── sql/
│   ├── create_schemas.sql
│   ├── gold_queries.sql
│
└── README.md
```

---

## 📥 **Data Ingestion (Bronze Layer)**

- Connect Databricks to AWS S3 using the built‑in integration.
- Ingest raw CSV files from:
  - **Full load** (July–Nov)
  - **Incremental load** (December)
- Add metadata columns:
  - `read_timestamp`
  - `file_name`
  - `file_size`

---

## 🧹 **Data Cleaning & Standardization (Silver Layer)**

Key transformations include:

- Removing duplicates  
- Fixing inconsistent city names  
- Standardizing capitalization  
- Handling missing values  
- Converting IDs to string  
- Creating harmonized fields:
  - `market`
  - `platform`
  - `channel`
- Creating unified customer names (e.g., `"Zanet Foods – Bangalore"`)

---

## 🧱 **Business Modeling (Gold Layer)**

- Align child company schema with parent company schema.
- Build a **star schema**:
  - **Dimensions**: Customers, Products, Pricing, Date
  - **Fact**: Orders
- Create a programmatic **Date Dimension** using PySpark.
- Prepare final tables for dashboard consumption.

---

## 📊 **Dashboard**

A unified dashboard is created to visualize:

- Sales performance  
- Customer segmentation  
- Product insights  
- Market trends  
- Parent vs. Child company comparisons  

The dashboard is powered by **Gold layer Delta tables**.

---

## 🤖 **Using Databricks Genie AI**

Throughout the project, Genie AI is used to:

- Generate SQL queries  
- Suggest PySpark transformations  
- Validate schema mappings  
- Speed up data cleaning logic  

This demonstrates how AI can accelerate data engineering workflows.

---

## 📈 **Key Learning Outcomes**

By completing this project, I learned how to:

- Build a full data pipeline on Databricks  
- Use AWS S3 as a data lake  
- Apply the Medallion Architecture  
- Clean and transform data with PySpark  
- Model data using a star schema  
- Handle full + incremental loads  
- Use AI to accelerate engineering tasks  
- Build a unified analytics layer for a real business scenario  

---

## 📌 **Next Steps**

- Add CI/CD with Databricks Repos  
- Implement Delta Live Tables  
- Add automated quality checks with **Expectations**  
- Deploy the dashboard to production  

---
