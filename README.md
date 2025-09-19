# ELT Pipeline with dbt, Snowflake & Airflow
[![dbt Docs](https://img.shields.io/badge/dbt-docs-blue)](https://shrek6201.github.io/elt_pipeline/)

End-to-end ELT pipeline transforming Snowflake TPCH sample data with **dbt** and orchestrating execution through **Apache Airflow (Astronomer Cosmos)**.

---

## 📖 Overview
This project demonstrates how to design and orchestrate a modern analytics pipeline:
- **Source:** Snowflake’s TPCH sample dataset (`tpch_sf1`)
- **Transform:** dbt models across *staging*, *intermediate*, and *marts* layers (`fct_orders`)
- **Test:** schema & data quality checks (`not_null`, `unique`, `relationships`)
- **Orchestrate:** Airflow DAG auto-generated from dbt’s manifest using Astronomer Cosmos
- **Document:** Published **dbt Docs** with lineage graph and metadata

👉 **[View the live dbt Docs](https://shrek6201.github.io/elt_pipeline/)**

---

## 🏗️ Architecture
Snowflake (TPCH data)
   → dbt (SQL models + tests)
   → Airflow (Cosmos DAG)
   → dbt Docs (lineage visualization)

## 📂 Repository Structure
.
├── models/
│   ├── staging/        # source → cleaned views
│   └── marts/          # fact & summary tables
├── tests/              # data quality SQL tests
├── macros/             # custom dbt macros
├── docs/               # published dbt docs site
├── dbt_project.yml     # dbt project config
└── README.md

---

## 🚀 Getting Started

### Prerequisites
- Python 3.10+  
- [dbt-core](https://docs.getdbt.com/docs/get-started/installation)  
- Access to [Snowflake](https://www.snowflake.com/) (or DuckDB for local run)  
- Apache Airflow (via [Astronomer Cosmos](https://github.com/astronomer/astronomer-cosmos))  

### Run dbt
# Install dependencies
dbt deps

# Run transformations
dbt run

# Run data quality tests
dbt test

# Generate documentation
dbt docs generate
dbt docs serve

## DAG Workflow
<img width="2550" height="1820" alt="image" src="https://github.com/user-attachments/assets/b344c5b4-d4af-40b5-bc5f-774677f1ff4e" />

