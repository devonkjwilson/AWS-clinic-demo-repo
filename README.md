This project demonstrates the design and implementation of an end-to-end healthcare operations analytics platform built on AWS. The system ingests operational clinic data from an API, processes it through a medallion-style architecture (Bronze, Silver, Gold), and serves curated datasets to a warehouse for reporting and analytics.
The goal of this repository is to show how modern data engineering patterns can be applied to real-world healthcare operations scenarios such as appointment tracking, visit cycle time analysis, provider utilization, and revenue event monitoring.
Architecture Overview
The platform is composed of the following layers:
Ingestion Layer
REST API providing clinic operational data (patients, providers, appointments, visit events, and charges)
Python ingestion jobs that retrieve data incrementally and store raw JSON in Amazon S3
Storage and Processing
Amazon S3 used as the data lake for raw and curated datasets
AWS Glue used to transform raw JSON into structured datasets
Data normalized and cleaned in a Silver layer using Spark transformations
Analytics Layer
Amazon Redshift Serverless used as the analytics warehouse
Gold layer tables structured in a dimensional model to support reporting and BI tools
Orchestration
Apache Airflow used to coordinate ingestion, transformation, and loading workflows
Visualization
Power BI or Amazon QuickSight used to build dashboards for operational reporting
