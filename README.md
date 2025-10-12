# Ingestion and Transformation of Multiple Daily Files from a Shared Folder to Azure Cloud

**Repository:** azure-file-ingestion-pipeline

This repository contains a data pipeline designed to ingest multiple daily files from a shared folder, transform the data as required, and load it into Azure Cloud storage. It leverages Azure-native services to ensure reliability, scalability, and maintainability.

## Features

- **Daily File Ingestion:** Automatically fetch files from a shared folder every day.
- **Data Transformation:** Apply configurable transformations to prepare data for downstream processes.
- **Azure Integration:** Supports Azure Data Lake and other Azure services.
- **Scalable and Reliable:** Built for enterprise-level file volumes and robust error handling.

## Architecture Overview

**1. Data Source (On-Prem Shared Folder / CSV Files)**

   - 100+ raw CSV files generated daily from business systems or shared drives.
   - Files vary in schema and size and are automatically detected and processed.
     
**2. Azure Data Factory (ADF)**
     
   - Orchestrates the entire ETL process using pipelines and triggers.
   - Uses a Self-Hosted Integration Runtime (IR) to securely connect to on-prem file shares.
   - Copies data into Azure Data Lake Storage Gen2 (ADLS) raw zone.
   - Supports dynamic ingestion using metadata-driven configuration.
     
**3. Azure Data Lake Storage (ADLS)**
     
   - Centralized data repository with bronze (raw), silver (cleaned), and gold (curated) zones.
   - Provides secure, scalable storage for structured and semi-structured data.
     
**4. Azure Databricks**
     
   - Performs data cleansing, schema harmonization, and transformation using PySpark notebooks.
   - Supports schema drift handling and incremental loading.
   - Writes processed data back to ADLS in Parquet/Delta formats for optimized analytics.
     
**5. Azure Synapse Analytics**
   - Serves as the enterprise data warehouse layer.
   - Consumes curated datasets from ADLS via serverless or dedicated SQL pools.
   - Enables analytical queries, joins, and business logic modeling.
     
**6. Power BI**
     
   - Connects directly to Synapse or curated ADLS layers via Power BI Dataflows or DirectQuery.
   - Delivers interactive dashboards and business insights refreshed daily.
     
## Getting Started

1. Clone this repository:
   ```bash
   git clone https://github.com/your-org/azure-file-ingestion-pipeline.git
