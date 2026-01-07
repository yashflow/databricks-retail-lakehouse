# Retail Sales Analytics Lakehouse (Databricks)

## Project Overview
This project demonstrates how to build an end-to-end **Retail Analytics Lakehouse** using Databricks and Delta Lake.  
The goal is to transform raw retail transaction data into clean, reliable, and analytics-ready datasets using the **Medallion (Bronze–Silver–Gold) architecture**.

---

## Tech Stack
- Databricks Community Edition  
- Apache Spark (PySpark)  
- Delta Lake  
- SQL  

---

## Dataset
- **Source:** Online Retail Dataset (Kaggle / UCI)
- **Type:** Retail transaction data
- **Key Columns:**  
  `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `UnitPrice`, `InvoiceDate`, `CustomerID`, `Country`

> The raw dataset is not stored in this repository.  
> Instructions to download and upload the data are provided in the `data/` folder.

---

## Architecture Overview
The project follows a **Bronze → Silver → Gold** Lakehouse design pattern.

- **Bronze Layer:** Stores raw data with minimal transformation and ingestion metadata.
- **Silver Layer:** Cleans and standardizes data by applying business rules and data quality checks.
- **Gold Layer:** Provides aggregated, business-ready tables for analytics and reporting.

An architecture diagram is available in the `docs/` folder.

---

## Pipeline Layers

### Bronze Layer
- Ingest raw retail data from Databricks Catalog
- Preserve original records
- Add ingestion metadata
- Output table: `bronze_sales`

### Silver Layer
- Remove cancelled invoices and invalid records
- Handle nulls and incorrect values
- Standardize data types
- Derive business columns (e.g., total revenue)
- Output table: `silver_sales`

### Gold Layer
- Create analytics-ready aggregated tables:
  - Daily revenue
  - Top products
  - Top customers
  - Revenue by country

---

## Repository Structure
