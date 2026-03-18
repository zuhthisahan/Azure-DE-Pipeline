# Azure Lakehouse ETL Pipeline with Databricks & Synapse

This project implements an end-to-end data engineering pipeline using Azure services.  
The pipeline loads data from a local MySQL database into Azure Data Lake Storage Gen2, 
transforms the data using Databricks with a Bronze–Silver–Gold architecture, and exposes 
the final data through Azure Synapse SQL views for reporting.

## Architecture

Local MySQL → Azure Data Factory → ADLS Gen2 (Bronze)
→ Databricks (Bronze → Silver → Gold)
→ Azure Synapse SQL (Views / Stored Procedures)
→ Power BI

## Technologies Used

- Azure Data Factory
- Azure Databricks
- Azure Data Lake Storage Gen2
- Azure Synapse Analytics
- MySQL (local server)
- Delta Lake
- PySpark
- SQL

## Pipeline Steps

1. Source data stored in local MySQL server
2. Azure Data Factory pipeline copies data to ADLS Gen2 (Bronze layer)
3. Databricks notebooks transform data into Silver and Gold layers using Delta tables
4. Azure Synapse stored procedures create views from Gold layer tables
5. Views are used as reporting tables for Power BI

## Data Layers

Bronze  
Raw data copied from MySQL without transformation

Silver  
Cleaned and structured data

Gold  
Business-ready tables used for analytics and reporting

## Notes

- Cluster used: single node Databricks cluster (student subscription)
- Storage: Azure Data Lake Gen2
- Orchestration: Azure Data Factory pipeline trigger
- Query layer: Synapse SQL views
