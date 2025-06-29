# Smart_City_End_to_End_DataEngineering_Project

![Architecture Diagram](https://github.com/DivineSamOfficial/SmartCityProject/blob/main/Analysis-1.png)

# Smart City End to End Real-Time Data Streaming Pipeline

## Project Overview

This project aims to create a comprehensive real-time data streaming pipeline for a Smart City initiative. It captures and processes real-time data from a vehicle traveling from London to Birmingham, including vehicle data, GPS data, emergency incidents, weather conditions, and camera footage. The pipeline leverages a combination of IoT devices, Apache Kafka, Apache Spark, Docker, and AWS services to ensure efficient data ingestion, processing, storage, and visualization.

## Architecture Overview

![Architecture Diagram](https://github.com/DivineSamOfficial/SmartCityProject/blob/main/SysArch.png)

## Technologies Used

- **IoT Devices**: For capturing real-time data.
- **Apache Zookeeper**: For managing and coordinating Kafka brokers.
- **Apache Kafka**: For real-time data ingestion into different topics.
- **Apache Spark**: For real-time data processing and streaming.
- **Docker**: For containerization and orchestration of Kafka and Spark.
- **Python**: For data processing scripts.
- **AWS Cloud**:  
  - **S3**: For storing processed data as Parquet files.  
  - **Glue**: For data extraction and cataloging.  
  - **Athena**: For querying processed data.  
  - **IAM**: For managing access and permissions.  
  - **Redshift**: For data warehousing and analytics.
- **Amazon QuickSight**: For data visualization and dashboarding.

## Project Workflow

1. **Data Ingestion**  
   - IoT devices capture real-time data.  
   - Data is ingested into Kafka topics configured in Docker using `docker-compose.yml`.

2. **Data Processing**  
   - Apache Spark reads data from Kafka topics.  
   - Spark processes the data and writes it to AWS S3 as Parquet files.  
   - Spark Streaming is used for real-time data processing with checkpointing to handle data issues.

3. **Data Storage**  
   - Processed data is stored in AWS S3.  
   - AWS Glue crawlers extract data from S3 and catalog it.

4. **Data Querying**  
   - AWS Athena queries the processed and cataloged data from Glue.

5. **Data Visualization**  
   - Amazon QuickSight visualizes the queried data with interactive dashboards.

## Getting Started

### Prerequisites

- Docker and Docker Compose  
- AWS Account with appropriate IAM roles and permissions  
- Python 3.x  
- Apache Kafka and Apache Spark setup  

### Setup Instructions

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/SmartCityProject/smart-city-pipeline.git
   cd smart-city-pipeline
