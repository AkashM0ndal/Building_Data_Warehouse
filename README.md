# Building_Data_Warehouse

This repository contains a **SQL-based ETL pipeline** that processes raw data into **clean, optimized, and analytics-ready datasets** using a **multi-layered (Bronze / Silver / Gold) architecture**.

- ✅ Handles **60,000+ records**
- ✅ Works across **6+ relational tables**
- ✅ Uses **Schemas, Stored Procedures, and CTEs**
- ✅ Designed for **scalable analytics and reporting**

---

## 🚀 Project Overview

The goal of this project is to:

1. **Ingest** raw data into the database (Bronze layer).  
2. **Clean, transform, and standardize** data (Silver layer).  
3. **Model optimized tables for reporting and analysis** (Gold layer).  

This architecture follows modern data engineering best practices, ensuring maintainability, traceability, and performance.

---

## 🏗️ Architecture: Bronze / Silver / Gold

The pipeline uses three logical schemas:

- **`bronze` schema** – Raw or minimally processed data.
- **`silver` schema** – Clean, standardized, relational data.
- **`gold` schema** – Business-ready analytical datasets.

📂 Schema & Table Design
🥉 Bronze Schema – bronze

Purpose: Raw landing zone
Characteristics:

Minimal transformations

Source structure preserved

Includes timestamps for lineage

Example tables:

bronze.customers_raw

bronze.orders_raw

bronze.products_raw

bronze.stores_raw

bronze.payments_raw

bronze.shipments_raw

🥈 Silver Schema – silver

Purpose: Cleaned and standardized data
Characteristics:

Data quality checks

Normalized formats

Deduplication

Referential integrity corrections

Example tables:

silver.customers

silver.orders

silver.products

silver.payments

silver.stores

silver.shipments

🥇 Gold Schema – gold

Purpose: Analytics & BI-ready models
Characteristics:

Fact & dimension tables

Aggregated or denormalized

Optimized for reporting

Example tables:

gold.fact_sales

gold.fact_revenue_daily

gold.dim_customer

gold.dim_product

gold.dim_store

⚙️ ETL Logic: Stored Procedures & CTEs

The transformation logic is implemented using:

Stored Procedures

sp_load_bronze (optional, if you stage raw loads via procedure)

sp_transform_bronze_to_silver

sp_transform_silver_to_gold

sp_run_full_etl (optional master procedure)

CTEs

Used for:

Cleaning and standardizing data

Joining tables

Step-by-step business rules

Example CTE-based transformation:
