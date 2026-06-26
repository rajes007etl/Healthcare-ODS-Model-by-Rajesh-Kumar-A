# Healthcare ODS Data Platform – Rajesh Kumar A

## 📌 Overview
This repository demonstrates an **end‑to‑end Healthcare Operational Data Store (ODS)** built using **Azure Data Factory (ADF)** and **Databricks**.  
It follows the industry‑standard **Bronze → Silver → Gold** data layering approach, with orchestration and version control integrated via GitHub.

---

## 🏗️ Architecture

CSV → Blob → ADF (Bronze) → Databricks (Silver/Gold) → BI

### Bronze Layer (Raw Ingestion)
- Implemented using **Azure Data Factory (ADF)** pipelines.
- **Landing CSV files** from source systems (Claims, Members, Providers, Payments) are stored in **Azure Blob Storage**.
- ADF pipelines load these CSVs into the Bronze Delta tables for traceability and audit.

### Silver Layer (Cleansed & Standardized)
- Implemented using **Databricks notebooks**.
- Applies transformations, deduplication, and Slowly Changing Dimension (SCD2) logic.
- Produces standardized Delta tables ready for analytics.

### Gold Layer (Curated for BI)
- Implemented using **Databricks notebooks**.
- Builds fact and dimension tables:
  - Fact_Claim  
  - Fact_Payment  
  - Dim_Member  
  - Dim_Provider  
  - Dim_Date
- Designed for BI tools such as Power BI or Tableau.

### Orchestration
- A **Master Notebook** in Databricks orchestrates Silver and Gold layers.
- Bronze handled by ADF, Silver/Gold handled by Databricks.
- Jobs scheduled via Databricks Workflows.

### Version Control
- All ADF JSON definitions and Databricks notebooks are stored in this GitHub repository.
- Enables collaboration, CI/CD, and professional portfolio visibility.

---

## 📂 Repository Structure

/adf
/pipelines
/datasets
/linkedServices
/triggers

/databricks
/COMMON
/SILVER
/GOLD
/JOBS
/DB SETUP

README.md
---

## 🚀 Key Highlights
- Hybrid architecture: **ADF for ingestion**, **Databricks for transformation**.
- Industry‑standard **Bronze → Silver → Gold** layering.
- **Master Notebook orchestration** for Silver & Gold.
- **GitHub integration** for version control and portfolio showcase.
- Designed for **Healthcare domain** (Claims, Members, Providers, Payments).

---

## 📊 Use Case
This project simulates a **Healthcare ODS** where:
- Raw claims and member data are ingested via ADF.
- Cleansed and standardized in Databricks Silver layer.
- Curated into Gold fact/dimension tables for BI reporting.
- Enables insights into claims processing, provider performance, and payment trends.

---

## 👨‍💻 Author
Rajesh Kumar A
Technical Lead |Data Engineer | Azure | Databricks | SQL | ETL | Healthcare Data Platforms | E-Commerce
