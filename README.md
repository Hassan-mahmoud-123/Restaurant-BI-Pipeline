# 🍴 Restaurant BI: Scalable Cloud Data Pipeline (11M+ Records)

## 🌟 Executive Summary
This project showcases an end-to-end Big Data solution, transforming **11 Million+ records** from fragmented sources (CSV & JSON) into a high-performance interactive dashboard. By leveraging **Cloud Infrastructure**, I bypassed local hardware limitations to deliver a real-time analytical tool.

---

## 🏗️ Architecture & Workflow

### 1. Data Ingestion (Cloud-to-Cloud)
- **Source:** 9 Large-scale files (CSV/JSON) hosted on **Google Drive**.
- **Ingestion:** Established a public API connection between Google Drive and **Databricks** to automate data fetching, avoiding manual uploads and local storage bottlenecks.

### 2. ETL & Data Engineering (The Heavy Lifting)
- **Unified Processing:** 
  - Integrated multiple **CSV** sources into a unified Spark DataFrame.
  - Parsed complex **JSON** files and flattened them into relational tables.
  - Performed a **Full Outer Join** to create a master "Golden Record" dataset.
- **Data Cleaning:** Handled inconsistent **Data Types** (specifically converting malformed Date strings) using PySpark to ensure time-series accuracy.
- **Optimization:** Processed everything in the **Databricks Spark Engine**, which proved significantly faster than Power BI’s Power Query for a dataset of this magnitude.

### 3. Power BI Integration (DirectQuery Mode)
- **Connectivity:** Linked Power BI to Databricks via **DirectQuery**.
- **The Advantage:** By using DirectQuery, the "Heavy Lifting" (Processing/Aggregations) stays in the **Cloud Engine**, ensuring the dashboard remains fast and responsive without needing to load 11M rows into the local RAM.

---

## 🛠️ Tech Stack
| Phase | Tool |
| :--- | :--- |
| **Storage** | Google Drive |
| **ETL / Processing** | Databricks (Apache Spark) |
| **Language** | Python (PySpark) & SQL |
| **Visualization** | Power BI (DirectQuery) |

---

## 📊 Key Insights & Results
- **Performance:** Reduced data refresh and transformation time by **~80%** compared to traditional local processing.
- **Scalability:** The pipeline is built to handle future data growth without hardware upgrades.
- **Insights:** Enabled real-time tracking of KPIs across all branches in Egypt with zero lag.

---

## 📂 Repository Contents
- `dataset-sample/`: A representative sample (5,000 rows) of the processed data.
- `Databricks_Notebook.ipynb`: The complete Python/SQL code for the ETL pipeline.
- `Restaurant_Analysis.pbix`: The Power BI report file (Optimized for DirectQuery).
- `Screenshots/`: Visual evidence of the Dashboard and Data Model.

---

## 💡 How to Run
1. View the `Databricks_Notebook.ipynb` to see the Spark transformations.
2. The PBIX file requires a Databricks SQL Warehouse connection to refresh live data.
