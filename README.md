# AzureDataFactory Taxi Data Pipeline

## 📋Project Description

This project demonstrates the creation of an end-to-end data pipeline on Microsoft Azure to process and analyze NYC Taxi trip data. It focuses on ingesting raw data, transforming it into a structured format, and loading it into a data warehouse for analytical purposes. This pipeline showcases the power of Azure's data services for building scalable and reliable data solutions.

## 👷🏼‍♂️Architecture:

The project architecture is designed to handle large volumes of data and consists of the following components:

* **Data Ingestion:** Fetch NYC Taxi Trip Data from APIs using Azure Data Factory(ADF) and load it into Azure Data Lake Storage(ADLS) Gen2.
* **Azure Data Lake Storage(ADLS) Gen2:** Used for storing raw and processed(cleaned) taxi trip data.
* **Azure Data Factory (ADF):** Orchestrates the data pipeline, including data ingestion, transformation, and loading.
* **Azure SQL Database:** Serves as the relational data warehouse for storing the structured, processed data, enabling efficient querying and analysis.

## 🛠Technologies Used:

* **Azure Data Lake Storage(ADLS) Gen2:**
* **Azure Data Factory (ADF):**
* **Azure SQL Database:**

## 💻Setup and Execution:

1.  **Azure Resource Setup:**
    * Provision Azure Storage account and Data Lake Storage.
    * Provision an Azure Data Factory instance.
    * Provision an Azure SQL Database instance.
2.  **Data Storage Configuration:**
    * Configure Data Lake Storage containers.
3.  **Azure Data Factory Configuration:**
    * Create linked services for Data Lake Storage and Azure SQL Database.
    * Develop ADF pipelines and Data Flow activities.
    * Configure datasets.
4.  **SQL Database Setup:**
    * Create database tables and schemas.
5.  **Execution:**
    * Trigger ADF pipelines.
    * Run SQL queries in Azure SQL Database.


## 🔀DataFlow

In this project, I:

* Designed and implemented an automated data pipeline using Azure Data Factory to ingest raw taxi trip data from Azure Data Lake Storage.
* Developed Data Flow activities in ADF to perform data cleaning, transformation, and schema mapping.
* Created SQL scripts for data normalization, type conversion, and data enrichment.
* Loaded the transformed data into Azure SQL Database table, optimizing for query performance.
* Implemented data validation and quality checks within the pipeline to ensure data accuracy.
* Automated the data pipeline using ADF triggers and scheduling, ensuring continuous and reliable data processing.
* Optimized the pipeline for performance and scalability to handle large datasets.
* Designed and created the table within the Azure SQL database.
* Created linked services, datasets, and pipelines within the Azure Data Factory.

## 🔑Key Takeaways:
This project significantly enhanced my skills in:
* Handling API data ingestion.
* Designing and implementing end-to-end cloud-based data pipeline.
* Working with large datasets and optimizing for performance.
* Automate the data pipeline using ADF triggers.
* Building relational data warehouses using Azure SQL DB. 
* The use and implementation of ADLS Gen2. 


## Sample SQL Queries

Query to find the average trip distance by pickup location.
```sql
SELECT
    pickup_zipcode,
    AVG(trip_distance) AS average_distance
FROM
    taxi_trips
GROUP BY
    pickup_zipcode
ORDER BY
    average_distance DESC;
```
Query to find the total number of trips per month.
```sql
SELECT
    DATEPART(year, pickup_datetime) AS trip_year,
    DATEPART(month, pickup_datetime) AS trip_month,
    COUNT(*) AS total_trips
FROM
    taxi_trips
GROUP BY
    DATEPART(year, pickup_datetime), DATEPART(month, pickup_datetime)
ORDER BY
    trip_year, trip_month;
```
Query to find the top 10 most expensive average trip fares per dropoff location.
```sql
SELECT top 10
    dropoff_zipcode,
    AVG(fare_amount) AS average_fare
FROM
    taxi_trips
GROUP BY
    dropoff_zipcode
ORDER BY
    average_fare DESC;
```

This project was a challenging yet rewarding experience, demonstrating the power of Azure cloud services for building scalable data solutions.

