# Data Observability Dashboard – Power BI

This repository contains the supporting mock data and documentation for a Power BI Data Observability dashboard.

## Purpose

The project demonstrates monitoring of data quality, missing values, data freshness, and file-level issues using Power BI, Power Query, and DAX.

> **Important:** The CSV files in this repository are mock/simulated data. No confidential internship source data is included.

## Repository Structure

```text
Data-Observability-PowerBI/
├── README.md
├── data/
│   ├── DataObservability_Mock.csv
│   ├── file_2025-04-05.csv
│   ├── file_2025-04-06.csv
│   └── file_2025-04-07.csv
├── dax/
│   └── DAX_Measures.md
└── docs/
    └── project-workflow.md
```

## Technologies

- Power BI
- DAX (Data Analysis Expressions)
- Power Query
- Data Quality Monitoring
- Data Observability
- Microsoft Fabric concepts

## Main Monitoring Checks

- Null `Amount` values
- Schema/data health status
- Null values by file date
- Daily record availability
- Data freshness/delay concepts
- Interactive date filtering

## Microsoft Fabric Relation

The current repository uses mock CSV data so that the project can be reproduced without access to the original enterprise environment.

A production architecture could use:

```text
Source Systems
    ↓
Data Ingestion
    ↓
Microsoft Fabric Lakehouse
    ↓
Spark / SQL transformations
    ↓
Data Quality Checks
    ↓
Power BI Dashboard
```

## Power BI File

The `.pbix` dashboard can be added to the `powerbi/` folder. GitHub repositories may have size limitations for large binary files, so Git LFS can be used if necessary.
