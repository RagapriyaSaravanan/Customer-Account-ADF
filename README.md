# Customer-Account-ADF

Order of files to go through
1. README
2. Prerequisites and Setup
3. Project Implementation
4. Code
5. Outputs

## Introduction

This project focuses on the design and implementation of an end-to-end data pipeline for customer account analysis, built using Microsoft Azure’s suite of data services. The objective is to build a robust, scalable pipeline capable of ingesting raw customer-related data from a backend storage account, transforming it using Azure Data Factory Dataflows, and storing the cleaned and processed output into an Azure SQL Database.

The project also integrates Power BI for reporting and dashboard creation, enabling end users to visualize customer and account insights effectively. The final result is a clean, layered pipeline with support for Slowly Changing Dimensions (SCD), dynamic configurations, and secure credential management via Azure Key Vault.

By building this pipeline, the student gains hands-on experience in data engineering best practices, including staging data using bronze, silver, and gold layers, handling historical data, automating data refreshes, and securing sensitive information—all essential skills in the modern data ecosystem.

---

## Prerequisites

Before beginning the project, the following prerequisites were fulfilled:

### Azure Services
- Azure Data Factory
- Azure Data Lake Storage Gen2
- Azure SQL Database
- Azure Key Vault
- Power BI
- Microsoft Fabric

### Data Source
On-premise backend storage access containing five CSV files:
- `accounts.csv`
- `customers.csv`
- `loan_payments.csv`
- `loans.csv`
- `transactions.csv`

### Knowledge Requirements
- Basic understanding of:
  - Data pipelines and ETL concepts
  - Azure Data Factory components (pipelines, datasets, dataflows)
  - SQL operations
  - SCD Type 1 and Type 2 logic
  - Power BI dashboard creation

---

## Concepts and Tools Used

### ETL (Extract, Transform, Load)
Data is extracted from the backend, transformed (cleaned, deduplicated, enriched), and loaded into an Azure SQL Database for reporting.

### Medallion Architecture
**Bronze Layer** – Raw ingested data with minimal transformation  
**Silver Layer** – Cleaned, deduplicated data for analytical processing  
**Gold Layer** – Curated, business-ready data optimized for Power BI

### Azure Data Factory (ADF)
Main orchestration engine using:
- Copy Activities
- Dataflows
- Execute Pipeline activities for modular workflows

### Azure Data Lake Storage Gen2 (ADLS Gen2)
- Hierarchical namespaces for structured folder-like organization
- Stores data in CSV, Parquet, and Delta formats across Bronze, Silver, and Gold layers

### Azure SQL Database
- Destination for Gold layer data
- Hosts dimension and fact tables
- Implements SCD Type 1 and Type 2 logic for updates and historical tracking

### Power BI
- Connects to Azure SQL Database for reporting
- Dashboards display insights like loan trends, account segmentation, etc.
- Published to Microsoft Fabric workspaces

### Slowly Changing Dimensions (SCD)
- **SCD Type 1**: Overwrites old records
- **SCD Type 2**: Maintains history with versioning using:
  - `is_active` flag

### Azure Key Vault
- Stores all sensitive credentials (e.g., connection strings, keys)
- Integrated with ADF using managed identities

---

## Orchestration 

- Master ADF Pipeline orchestrates three child pipelines:
  1. Bronze Ingestion
  2. Silver Transformation
  3. Gold SCD Loading
---
## Summary

The Customer-Account-ADF project is a comprehensive showcase of modern data engineering practices using Microsoft Azure. It illustrates:
- Full-lifecycle data management
- Efficient pipeline architecture
- Visualization with Power BI
- Security and scalability through Azure-native tools

This project not only delivers a high-impact business solution but also builds critical skills for real-world data engineering roles.

![image](https://github.com/user-attachments/assets/5df09d1c-e72b-4383-a9ba-8b28a912f241)

