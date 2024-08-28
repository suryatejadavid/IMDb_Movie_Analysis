# IMDb Quality Movie Data Analysis

## Overview

This project implements a batch processing system for analyzing IMDb quality movie data. Utilizing AWS services such as S3, Glue, Redshift, EventBridge, Athena, and QuickSight, the project facilitates efficient data processing and analysis. It also incorporates incremental data processing with robust data quality checks and event-driven SNS notifications, streamlining the analysis process and providing actionable insights through dynamic dashboards.

## Features

- **Batch Data Processing:** Leverages AWS Glue for ETL operations to process IMDb movie data in batches.
- **Incremental Data Processing:** Efficiently manages incremental data loads with built-in data quality checks.
- **Event-Driven Architecture:** Utilizes AWS EventBridge and SNS for event-driven notifications and processes.
- **Automated Data Quality Checks:** Ensures the integrity of data before it is loaded into Redshift for analysis.
- **Visualization:** Utilizes Amazon QuickSight to create dynamic dashboards for data visualization and insights.

## Architecture

The architecture consists of the following components:

1. **S3:** The primary storage for raw and processed IMDb movie data.
2. **Glue:** Handles the ETL process, transforming raw data into a format suitable for analysis.
3. **Redshift:** Stores the processed data for efficient querying and analysis.
4. **EventBridge:** Manages the event-driven architecture, triggering processes as new data becomes available.
5. **SNS:** Sends notifications based on data processing events.
6. **Athena:** Provides an SQL interface to analyze data directly from S3.
7. **QuickSight:** Visualizes the data, providing dashboards for insights into movie quality.

## Project Structure
imdb-quality-movie-analysis/
│
├── data/
│   └── imdb_movies_rating.csv                # Sample IMDb movie rating data
│
├── glue/
│   └── movies_quality_ingestion_glue.py      # Glue ETL script for processing movie data
│
├── assets/
│   └── architecture_diagram.png              # Architecture diagram (update with correct path)
│
└── README.md                                 # Project documentation (this file)

## Prerequisites

- **AWS Account:** Ensure you have an active AWS account.
- **Python 3.8+:** The scripts and Glue jobs are written in Python.
- **AWS CLI:** For managing AWS resources from the command line.

## Setup and Deployment

1. **S3 Bucket Creation:**
   - Create an S3 bucket to store raw and processed IMDb movie data.

2. **Glue Job Deployment:**
   - Use the `movies_quality_ingestion_glue.py` script to create a Glue ETL job.
   - Configure the Glue job to process the data stored in the S3 bucket and load it into Redshift.

3. **Redshift Cluster Setup:**
   - Set up an Amazon Redshift cluster to store processed data.
   - Configure Redshift to allow queries from Athena and data ingestion from Glue.

4. **EventBridge and SNS Configuration:**
   - Configure EventBridge rules to trigger Glue jobs based on specific events.
   - Set up SNS to send notifications when data processing events occur.

5. **QuickSight Setup:**
   - Set up QuickSight to connect to Redshift and create dashboards for visualizing the processed data.

## How It Works

1. **Data Ingestion:**
   - Raw IMDb movie data is ingested into the S3 bucket.
   - The Glue ETL job processes the raw data, performing necessary transformations and quality checks.

2. **Incremental Data Processing:**
   - The Glue job handles incremental data, ensuring only new or updated records are processed.
   - Data quality checks are performed during the ETL process to maintain data integrity.

3. **Event-Driven Notifications:**
   - EventBridge triggers the Glue job whenever new data is available.
   - SNS sends notifications upon successful data processing or if any errors are detected.

4. **Data Analysis and Visualization:**
   - Processed data is stored in Redshift, where it can be queried using Athena or visualized using QuickSight.
   - QuickSight dashboards provide insights into movie ratings, trends, and other key metrics.

## Benefits

- **Efficiency:** The system efficiently processes large datasets with incremental updates, reducing redundant processing.
- **Data Integrity:** Automated data quality checks ensure the accuracy and reliability of the data.
- **Scalability:** The architecture is built on AWS, allowing it to scale easily with increasing data volumes.
- **Actionable Insights:** QuickSight dashboards provide dynamic, real-time insights into IMDb movie data.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue if you have any suggestions or improvements.

## Acknowledgments

- The project was developed using AWS services and Python.
- Special thanks to the AWS community for their extensive documentation and resources.
