# Exercise 1
You are one of the great data engineers at Space X. Your task is to help the missile of Elon Musk fly launch and land successfully.

## Business use case
Elon Musk wants to increase his success rate when launching new missiles into space. In order to achieve better insights in the teams achievements, he needs to obtain an overview of the past success/fails. We need to obtain a fast and queryable table with the needed metrics and dimensions to further analyse them in a dashboard.

## Functional requirements
Following attributes should be available for querying inside our PostgreSQL DWH:
- Name
- Launch year
- Launch success
- Landing success

## Technical requirements
The data should be loaded from sources (defined below) and saved inside our datalake (bronze - silver - gold).
After extracting the data, it should be saved in the bronze layer `dataplatform/data_raw`.
In order for our internal teams to use the data it should be transformed to parquet consisting
of the defined attributes from the functional analysis. `dataplatform/data_staged`.
Once the data has been collected inside of our datalake, we can then import it in our PostgreSQL DWH. `space_x_flights`

- Datasource:
    - https://github.com/r-spacex/SpaceX-API
    - https://api.spacex.land/graphql/

## Tools
- Nifi
- MinIO
- PostgreSQL
