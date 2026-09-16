# SQL Data Warehouse & Analytics Project

Building a modern data warehouse with SQL Server — covering the full pipeline from raw data ingestion through to business-ready analytics.

## 📖 Overview

This project is an end-to-end data engineering and analytics build. It takes raw CRM and ERP data delivered as CSV files and turns it into a clean, query-ready data warehouse using SQL Server, following the **Medallion Architecture** pattern (Bronze → Silver → Gold). On top of the warehouse, SQL-based analysis is used to surface insights on customer behavior, product performance, and sales trends.

It's designed as a portfolio-style project demonstrating practical skills in:

- SQL development
- Data architecture
- ETL pipeline design
- Dimensional (star schema) data modeling
- Data analytics & reporting

## 🏗️ Data Architecture

The warehouse is organized into three layers:

| Layer | Purpose |
|---|---|
| **Bronze** | Raw data, loaded as-is from source CSV files (CRM & ERP) into SQL Server. No transformation. |
| **Silver** | Cleansed, standardized, and normalized data — ready for modeling. |
| **Gold** | Business-ready data, modeled into a star schema (fact & dimension tables) for reporting and analytics. |

```
Source CSVs (CRM + ERP)
        │
        ▼
  ┌───────────┐
  │  BRONZE   │  Raw, unmodified ingestion
  └─────┬─────┘
        │
        ▼
  ┌───────────┐
  │  SILVER   │  Cleaned, standardized, validated
  └─────┬─────┘
        │
        ▼
  ┌───────────┐
  │   GOLD    │  Star schema, business-ready
  └─────┬─────┘
        │
        ▼
   Analytics & Reporting
```

## 🎯 Project Requirements

### 1. Data Warehousing (Data Engineering)

**Objective:** Consolidate sales data from two source systems into a single warehouse that supports analytical reporting.

- **Data sources:** ERP and CRM systems, provided as CSV files
- **Data quality:** Identify and resolve quality issues before modeling
- **Integration:** Merge both sources into one unified, analysis-friendly data model
- **Scope:** Latest snapshot only — historical tracking is out of scope
- **Documentation:** Clear data model documentation for both business and technical stakeholders

### 2. Analytics & Reporting (Data Analysis)

**Objective:** Deliver SQL-based insights into:

- Customer behavior
- Product performance
- Sales trends

## 📂 Repository Structure

```
sql-data-warehouse-project/
│
├── datasets/                  # Raw source data (ERP and CRM CSVs)
│
├── docs/                      # Documentation & architecture diagrams
│   ├── data_architecture.drawio   # Overall architecture diagram
│   ├── data_flow.drawio           # Data flow diagram
│   ├── data_models.drawio         # Star schema / data models
│   ├── etl.drawio                 # ETL techniques & methods
│   ├── data_catalog.md            # Dataset field descriptions & metadata
│   └── naming-conventions.md      # Naming rules for tables, columns, files
│
├── scripts/                   # SQL scripts for ETL and transformation
│   ├── bronze/                    # Extract & load raw data
│   ├── silver/                    # Clean & transform data
│   └── gold/                      # Build analytical (star schema) models
│
├── tests/                     # Data quality / validation scripts
│
├── README.md                  # Project overview (this file)
├── LICENSE                    # License information
└── .gitignore                 # Files/directories excluded from Git
```

## 🛠️ Tools & Tech

- **SQL Server Express** — database engine
- **SQL Server Management Studio (SSMS)** — database GUI
- **Draw.io** — architecture, ETL, and data flow diagrams
- **Git / GitHub** — version control and collaboration

## 🚀 Getting Started

1. Clone the repository:
   ```bash
   git clone https://github.com/Himanshidhiman/sql-data-warehouse-project.git
   ```
2. Install SQL Server Express and SSMS if you don't already have them.
3. Run the Bronze-layer scripts in `scripts/bronze/` to load the raw CSVs from `datasets/` into SQL Server.
4. Run the Silver-layer scripts in `scripts/silver/` to clean and standardize the data.
5. Run the Gold-layer scripts in `scripts/gold/` to build the star schema used for analytics.
6. Explore `docs/` for the architecture diagrams and data catalog before diving into the scripts.

## 📊 What You Can Analyze

Once the Gold layer is built, the star schema supports queries and reports on:

- Customer segmentation and behavior
- Product performance
- Sales trends over time

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.
