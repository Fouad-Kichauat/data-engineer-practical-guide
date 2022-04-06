# Exercise 2
You are one of the great data engineers at a major company looking to invest in some great publicity. The company believes that they need to invest in some advertisement in the F1-races. Your task is to help the company determine the best drivers and car manufacturers they should sponsor during those races.

## Business use case
The company you work for wants to increase its visibility by participating in a sponsorship with f1-drivers/car manufacturers. In order for them to choose the right driver/brand to sponsor, they have asked you to provide them with insights about whom to choose based on past and possible future winnings. We need to obtain a fast and queryable **dimensional model** with the needed metrics and dimensions to further analyse them in a dashboard.

Additionally the data pipeline should be **idempotent**, i.e. when running the pipeline again the result should stay the same.

## Functional requirements
The end user wants a kimball model describing the needed tables between seasons, drivers, and constructors available for querying inside our PostgreSQL DWH.

Questions needed to be answered:
- What are the top brands based on the number of won seasons/races/top-drivers.
- What are the top drivers based on the number of won seasons/races.

## Technical requirements
The data should be loaded from sources (defined below) and saved inside our datalake (bronze - silver - gold).
After extracting the data, it should be saved in the bronze layer `dataplatform/data_raw`.

In order for our internal teams to use the data it should be transformed to parquet consisting of the defined attributes from the functional analysis. `dataplatform/data_staged`.

The dimensional modelling (Kimball) can happen on the datalake before ingestion in the DWH. The location should be `dataplatform/data_product`

Once the data has been collected inside of our datalake, we can then import it in our PostgreSQL DWH. `f1_races`

Datasource:
- http://ergast.com/mrd/

## Tools
You can solve the assignment using following three setups. The resulting solution should always consist of the same requested tables in our DWH (PostGresQL).
### Setup 1
- Nifi
- MinIO
- PostgreSQL

### Setup 2
- Apache Airflow
- Apache Spark
- MinIO
- PostgreSQL

### Setup 3
- Nifi
- Kafka
- MinIO
- PostgreSQL



## Additional exercises
1. Try to find out what additional metric/dimension would be interesting to have in our DWH and extract them from the source.
2. Make sure your pipeline is scheduled to run on a continuous basis to capture new data on a regular basis.
3. Try to visualize the results found in the DWH with your visualization tool of choice.
