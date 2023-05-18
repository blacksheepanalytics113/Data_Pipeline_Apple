# Data_Pipeline_Apple

# Architecture Diagram
![Screenshot (138)](https://github.com/adunajiye/Data_Pipeline_Apple/assets/80220180/5d6eaf1f-b79c-445b-9f73-3f98b9852999)

# Description

This project involves an ETL (Extract, Transform, Load) process to analyze sleep data exported from Apple Health to iCloud in XML format.

The data is then processed and transformed using AWS services, queried through Amazon Athena, and visualized using a Apache Superset dashboard.

# Project Overview
1. Export Health Data from iPhone to iCloud in XML format.
2. Load the data into an Amazon S3 bucket.
3. Set up an AWS Lambda function to process the XML data into a CSV file and store it in the S3 bucket.
4. Set up another AWS Lambda function to further transform the data using DuckDB and Pandas.
5. The data is then redirected to a Lambda Function, which saves the data as Parquet files in an S3 Bucket, partitioned by year.
6. Set up AWS Glue Crawlers to crawl the Parquet files stored in the S3 bucket and store the data in the AWS Glue Data Catalog table, partitioned by year.
7. Finally, A Streamlit dashboard is set up on an Amazon EC2 instance to display sleep analytics over the years.

