# Azure End-to-End ETL Pipeline - Sales Analysis
This project tackles a sample business requirement by developing an end-to-end data pipeline on Azure. The objective is to extract customer and sales data from an on-premises SQL database, transform it in the cloud, and deliver actionable insights via a Power BI dashboard. The dashboard will showcase key performance indicators (KPIs) such as gender distribution and product category sales, enabling stakeholders to filter and analyze data by product category, and gender for informed decision-making. The Azure pipeline is designed as a batch processing system, with a feature to automatically refresh data every 24 hours (disabled due to server resource limitations).

A visual representation of the pipeline (created in Lucidchart):


![etl-pipeline](https://github.com/radielazazy/azure-end-to-end-sales/blob/e2149661e03c6ae65b79fd8a426cd83c4c27f2f8/etl-pipeline.png)

## Technology Stack
Azure Data Factory (ADF): For orchestrating data movement and transformation.
Azure Data Lake Storage (ADLS): For storing raw and processed data.
Azure Databricks: For data transformation and processing.
Azure Synapse Analytics: For data warehousing and SQL-based analytics.
Power BI: For data visualization and reporting.
Azure Key Vault: For securely managing credentials and secrets.
SQL Server (On-Premises): Source of customer and sales data.
