# Azure End-to-End ETL Pipeline - Sales Analysis
This project tackles a sample business requirement by developing an end-to-end data pipeline on Azure. The objective is to extract customer and sales data from an on-premises SQL database, transform it in the cloud, and deliver actionable insights via a Power BI dashboard. The dashboard will showcase key performance indicators (KPIs) such as gender distribution and product category sales, enabling stakeholders to filter and analyze data by product category, and gender for informed decision-making. The Azure pipeline is designed as a batch processing system, with a feature to automatically refresh data every 24 hours (disabled due to server resource limitations).

# ETL Pipeline
(created in Lucidchart)
![etl-pipeline](https://github.com/radielazazy/azure-end-to-end-sales/blob/e2149661e03c6ae65b79fd8a426cd83c4c27f2f8/etl-pipeline.png)

## Technology Stack
* Azure Data Factory (ADF): For orchestrating data movement and transformation.
* Azure Data Lake Storage (ADLS): For storing raw and processed data.
* Azure Databricks: For data transformation and processing.
* Azure Synapse Analytics: For data warehousing and SQL-based analytics.
* Power BI: For data visualization and reporting.
* Azure Key Vault: For securely managing credentials and secrets.
* SQL Server (On-Premises): Source of customer and sales data.


## Steps for Setup
### Step 1: Azure Environment Setup
1. Create Resource Group: Set up a new resource group in Azure.
2. Provision Services:
    * Create an Azure Data Factory instance.
    * Set up Azure Data Lake Storage with bronze, silver, and gold containers.
    * Set up an Azure Databricks workspace and Synapse Analytics workspace.
    * Configure Azure Key Vault for secret management.
### Step 2: Data Ingestion
1. Set up SQL Server: Setup SQL Server and SQL Server Management Studio (SSMS). Restore the AdventureWorks database.
2. Ingest Data with ADF: Create pipelines in ADF to copy data from SQL Server to the bronze layer in ADLS.
### Step 3: Data Transformation
1. Mount Data Lake in Databricks: Configure Databricks to access ADLS.
2. Transform Data: Use Databricks notebooks to clean and aggregate the data, moving it from bronze to silver and then to gold.
### Step 4: Data Loading and Reporting
1. Load Data into Synapse: Set up a Synapse SQL pool and load the gold data for analysis.
2. Create Power BI Dashboard: Connect Power BI to Synapse and create visualizations based on business requirements.
### Step 5: Automation and Monitoring
1. Schedule Pipelines: Use ADF to schedule the data pipelines to run daily.
2. Monitor Pipeline Runs: Use the monitoring tools in ADF and Synapse to ensure successful pipeline execution.
### Step 6: Security and Governance
1. Manage Access: Set up role-based access control (RBAC) using Azure Entra ID (formerly Active Directory).
### Step 7: End-to-End Testing
1. Trigger and Test Pipelines: Insert new records into the SQL database and verify that the entire pipeline runs successfully, updating the Power BI dashboard.

## PowerBI Dashboard
PowerBI Dasboard screenshot can be seen below: [click this link to download](./ProductSalesAnalysis.pbix)
.

![powerbi](https://github.com/radielazazy/azure-end-to-end-sales/blob/a3bf9627908cc2b62ccb022910df331ef34ab034/pics-for-readme/Screenshot%202025-02-13%20040005.png)
