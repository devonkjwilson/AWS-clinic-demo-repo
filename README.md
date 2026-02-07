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


Data Flow
API data is ingested and stored in S3 as raw Bronze data
Glue jobs transform and standardize data into Silver tables
Curated dimensional models are built in Redshift (Gold layer)
BI tools query Gold tables for reporting and analysis
Key Features Demonstrated
Cloud-native data lake architecture
Incremental API ingestion patterns
Spark-based transformations
Dimensional modeling and SQL analytics
Workflow orchestration using Airflow
Operational healthcare analytics use cases
Business Use Cases Modeled
The platform supports analysis of:
Appointment volume and completion rates
Patient visit cycle time and wait time
Provider utilization and scheduling efficiency
Cancellation and no-show trends
Revenue and payment timing metrics
