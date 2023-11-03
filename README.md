# Spotify End-to-End ETL Data Engineering Project using Python and AWS

## Description:
In this project, we aim to create an ETL (Extract, Transform, Load) pipeline by leveraging the Spotify API on the AWS cloud platform. The pipeline's primary purpose is to retrieve data from the Spotify API concerning the top 50 global songs, transform this data into a desired format, and subsequently store it in an AWS data repository. 

## Pipeline Overview:
The project can be divided into three primary phases:
## 👉Extract:
 - The initial step involves extracting data from the Spotify API, which is executed using Python, facilitated by the Spotipy library.
 - AWS Lambda is employed to deploy the extraction function.
 - Automation is achieved using AWS CloudWatch to trigger the extraction function at regular intervals.
 - The raw extracted data is stored in an AWS S3 Bucket within the "to_processed" folder.

## 👉Transform:
 - The transformation phase begins by setting up S3 triggers to activate a second function whenever new data is deposited in the S3 Bucket.
 - Data transformation is performed using another AWS Lambda function.
 - The transformed data is stored in the S3 Bucket, distributed across different folders categorizing it by Album, Artist, and Song. It also involves moving data from the "to_processed" folder to the "processed" folder.

## 👉Load:
 - For schema inference, Glue Crawler is employed whenever new data is added to the S3 Bucket.
 - An AWS Glue Data Catalog is established to manage the Metadata Repository.
 - The final dataset is made queryable and analyzable using Amazon Athena, enabling users to obtain desired information from the data.

## Architecture:
![Architecture diagram](https://github.com/username/repository/raw/main/images/logo.png)

## Here's a list of the AWS services used in this project🔎:

**1. AWS Lambda:**
 - Used for deploying functions to extract data from the Spotify API and perform data transformation.
 - Also utilized to automate and schedule triggers for data extraction.

**2. Amazon S3 (Simple Storage Service):**
 - Served as a storage repository for both raw and transformed data.
 - Data was organized into folders.

**3. Amazon CloudWatch:**
 - Used for monitoring and scheduling the triggers for data extraction from the Spotify API.

**4. AWS Glue:**
 - Glue Crawler was employed to infer schema information whenever new data was added to the S3 Bucket.
 - An AWS Glue Data Catalog was created to manage metadata.

**5. Amazon Athena:**
 - Utilized for querying and analyzing the final dataset to extract the desired information.

These AWS services collectively provided the infrastructure and tools necessary to build and maintain your ETL data pipeline, ensuring data extraction, transformation, and loading tasks were efficiently carried out on the AWS cloud platform.

