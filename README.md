# Data_Pipeline_Apple

# Architecture Diagram
![Screenshot (138)](https://github.com/adunajiye/Data_Pipeline_Apple/assets/80220180/5d6eaf1f-b79c-445b-9f73-3f98b9852999)]

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
7. Finally, A Superset dashboard is set up on an Amazon EC2 instance to display sleep analytics over the years.


# Teck Stacks
1. AWS Services : S3, Lambda, Glue, Athena, SNS, EC2
2. Python Libraries : boto3, lxml, s3fs, awswrangler, pandas,Apache Superset
3. Data Processing : Pandas
4. Analytics and Visualization : Athena,Superset


The above tech stack and an iCloud Account with Apple Health Data synced regularly from Apple Watch are required. If you don't have an account, you can download my [Health Dataset](C:\Users\AjiyeAdunoluwa\Downloads\apple_health_export (1))


# Install Apache Superset with Docker on Ec2
 1. Ensure that Docker is installed on your system. You can download and install Docker from the official [Docker website](https://www.docker.com/get-started)
 2. Pull Superset Docker Image: Open a terminal or command prompt and execute the following command to pull the Superset Docker image:
    <b>docker pull apache/superset</b>
 3. Run Superset Container: Once the image is downloaded, run the Superset container using the following command:
   <b>docker run -d --name superset -p 8088:8088 apache/superset</b>
 4. Access Superset Web UI: Open a web browser and visit http://localhost:8088. This will take you to the Superset web user interface.
  

