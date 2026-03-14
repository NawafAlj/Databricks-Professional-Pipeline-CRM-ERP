# 🚀 Databricks Data Engineering Professional Pipeline: CRM & ERP

**Project Goal:** To transition from a basic scripting approach to a production-grade, governed, and automated Data Product. This project serves as a comprehensive practical guide for the **Databricks Certified Data Engineer Associate (2026)** exam, covering the full intelligence platform lifecycle.

---

## 🏗️ Project Architecture
This project implements a **Medallion Architecture** using **Lakeflow (Delta Live Tables)** and **Databricks Asset Bundles (DABs)**, managed entirely within **Unity Catalog**.

### 1. Ingestion (Bronze Layer)
* **Service:** Auto Loader (`cloudFiles`)
* **Exam Domain:** *Development and Ingestion*
* **Description:** Incremental ingestion of CRM and ERP CSV files from Google Cloud Storage (GCS).
* **Key Skills:** * **Schema Evolution:** Handling new columns automatically without pipeline failure.
    * **Rescued Data Column:** Capturing malformed records for audit and recovery.

### 2. Processing & Quality (Silver Layer)
* **Service:** Lakeflow / Delta Live Tables (DLT)
* **Exam Domain:** *Data Processing & Transformations*
* **Description:** Converting raw strings into high-quality, typed Delta tables with built-in validation.
* **Key Skills:**
    * **Expectations:** Implementing data quality constraints (e.g., `expect_or_drop` for invalid IDs).
    * **SCD Type 2:** Tracking historical changes in customer profiles via `APPLY CHANGES INTO`.
    * **Data Healing:** Logic-based standardization of gender and country codes.

### 3. Analytics & Serving (Gold Layer)
* **Service:** Delta Lake & SQL Warehouses
* **Exam Domain:** *Databricks Intelligence Platform*
* **Description:** A high-performance Star Schema optimized for Business Intelligence.
* **Key Skills:**
    * **Liquid Clustering:** Modern file layout optimization for rapid joins.
    * **Business Modeling:** Calculating sales metrics by region and product category.

### 4. Production & DevOps
* **Service:** Databricks Asset Bundles (DABs) & Workflows
* **Exam Domain:** *Productionizing Data Pipelines*
* **Description:** Managing the entire infrastructure-as-code (IaC) via the Databricks CLI.
* **Key Skills:**
    * **Serverless Compute:** Utilizing auto-optimized, managed compute.
    * **Repair & Rerun:** Strategies for task-level recovery in failed workflows.

### 5. Governance & External Integration
* **Service:** Unity Catalog
* **Exam Domain:** *Data Governance & Quality*
* **Description:** Centralized security, audit logs, and cross-platform connectivity.
* **Key Skills:**
    * **End-to-End Lineage:** Visualizing data flow from GCS raw files to final Gold tables.
    * **Lakehouse Federation:** Querying external sources (PostgreSQL/Snowflake) without data movement.
    * **Delta Sharing:** Securely sharing data with external partners.

---

## 🛠️ Tech Stack
* **Platform:** Databricks Intelligence Platform
* **Storage:** Google Cloud Storage (GCS)
* **Governance:** Unity Catalog (3-level Namespace)
* **Orchestration:** Databricks Workflows / DABs
* **Languages:** PySpark, Spark SQL

---

## 🚀 Deployment Instructions
1.  **Clone the Repo:** `git clone <repo_url>`
2.  **Auth:** `databricks auth login`
3.  **Validate:** `databricks bundle validate`
4.  **Deploy:** `databricks bundle deploy`
5.  **Monitor:** Check the **Jobs & Pipelines** UI in Databricks.

---

## 🎓 Exam Readiness Tracking
| Section | Key Feature Implemented |
| :--- | :--- |
| **Section 1** | Liquid Clustering & Serverless Compute |
| **Section 2** | Auto Loader & Schema Evolution |
| **Section 3** | DLT Pipelines & SCD Type 2 |
| **Section 4** | Asset Bundles (DABs) & Task Repair |
| **Section 5** | Managed vs. External Tables & Delta Sharing |