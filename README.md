# 🚀 Serverless CSV Data Pipeline – ETL

Serverless CSV data ingestion, transformation, and loading pipeline on AWS

## Short Description

Built a fully serverless ETL (Extract-Transform-Load) pipeline that automatically ingests CSV files uploaded to Amazon S3, transforms and cleans the data using AWS Lambda (and optionally AWS Glue), then loads the structured output into a target datastore or analytics layer—enabling scalable, event-driven data workflows.

## 🛠️ AWS Services Used:

Amazon S3,
AWS Lambda,
AWS Glue (optional for large batches),
Amazon DynamoDB (or Amazon Redshift/Athena for the target),
AWS IAM,

## 🧰 Technical Tools:

Python (for Lambda/tranformation code),
Boto3 (AWS SDK for Python),
AWS CLI / AWS SAM (for deployment),
CSV libraries & Pandas (for transformation),

## 🧠 Skills Demonstrated:

Event-driven data pipeline architecture,
Automated CSV ingestion and data cleansing,
Serverless transformation and loading of structured data,
Scalable ETL with cloud services and minimal infrastructure management,

## 📋 Steps Performed

### Create S3 Buckets and Enable Event Trigger:

Created an S3 bucket (e.g., `csv-data-raw`) to host incoming CSV uploads.
Configured an S3 event notification so that when a CSV file is uploaded, a Lambda function is triggered.

### Develop Lambda Function for Transformation:

Wrote a Lambda function that reads the uploaded CSV file from S3, cleans and transforms the data (e.g., parsing dates, handling missing values, mapping columns), converts the data to a structured format (JSON, Parquet or cleaned CSV), then writes the cleaned output to a staging S3 prefix (e.g., `processed/`).

### Load Transformed Data into Target Store:

From the staging location, configured the pipeline to load data into the target datastore—e.g., writing transformed records into DynamoDB table or triggering an Athena table/external catalog for analytics queries.

### Optional Glue Job for Large-Scale Transformation:

For large datasets, used AWS Glue to run a scale-out job (via Spark) reading CSV from S3, applying transformations, partitioning data, and writing optimized output format (e.g., Parquet) for consumption by analytics.

### Monitor, Log and Validate Pipeline:

Enabled CloudWatch logs and metrics to monitor the Lambda/Glue executions and failures. Tested the full flow by uploading sample CSVs, verifying data transformation, and querying the target store to validate correctness and completeness.

## ✅ Final Result:

Fully automated serverless CSV ETL pipeline

## 💼 Business Implication:

This project enables organizations to rapidly ingest and process CSV-based data sources (for example logs, partner feeds, or batch exports) in a scalable and cost-effective manner. By leveraging serverless architecture, the pipeline enables near-real-time readiness of structured data for analytics, simplifies data operations, and eliminates the need to manage infrastructure—helping teams focus on deriving insights and driving business value.
