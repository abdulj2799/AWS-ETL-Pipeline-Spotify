# AWS-ETL-Pipeline-Spotify
This project implements an ETL (Extract, Transform, Load) pipeline to collect, process, and analyze Spotify music data using AWS services. The pipeline extracts data from the Spotify API, processes it, and stores it in AWS for further analysis.

System Architecture
![Architecture](https://github.com/user-attachments/assets/9b276007-372c-462c-8620-7a4f90e9c342)

Spotify API Overview
The Spotify API enables developers to access Spotify’s extensive music database. It supports functionalities such as browsing music, managing playlists, searching tracks, and retrieving metadata on artists, albums, and songs. This project specifically uses the Top 50 - India playlist as the dataset.

AWS Services Used
Amazon S3 – Cloud-based storage for raw and processed data.
AWS CloudWatch – Monitors and triggers the ETL process on a scheduled basis.
AWS Glue Crawler – Automatically detects schema changes and updates the data catalog.
AWS Lambda – Serverless computing for handling data extraction and transformation.
Amazon Athena – SQL-based querying tool for analyzing data stored in S3.
AWS Data Catalog – Centralized metadata repository for structured queries in Athena.

Required Packages
pip install pandas
pip install boto3
pip install spotipy
pip install numpy


Execution Flow
CloudWatch triggers an AWS Lambda function weekly.
The Lambda function extracts music data from the Spotify API and stores it in S3’s raw data folder.
A second Lambda function processes and cleans the data, moving it to an S3 transformed data folder.
AWS Glue Crawler scans the stored data and updates the metadata in the Data Catalog.
Amazon Athena enables SQL-based querying for further analysis.
