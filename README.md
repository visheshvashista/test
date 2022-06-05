# Project: Data Warehouse with Redshift

Udacity Data Engineering Nanodegree. Songs and User log data is to be loaded in to Datawarehouse (Redshift) for processing. The data is loaded in to staging tables and then moved to dimension and fact tables.


## Files

1. ```create_table.py``` performs operations to create staging and dimensional tables
''' a. test '''

2. ```etl.py``` perform ETL process from staging tables, transform the data and load them into dimensional model tables.

3. ```sql_queries.py``` contains SQL queries for creating tables and load the data.

4. ```dwh.py``` contains the configuration for the project. It has details of the buckets from where data is to be loaded, Redshift Cluster to connect  and IAM role used.


## Database schema design

Staging tables to load raw data from S3 buckets

1. ```staging_events``` 
2. ```staging_songs```

Dimension tables

1. ```users```
2. ```songs```
3. ```artists```
4. ```time```

Fact table

1. ```songplays```

## Setting up project

1. Set up the Redshift Cluster.
2. Attach S3 Access policy to the Cluster.
3. Set up IAM role.
4. Update the dwh.cfg with the details of cluster and IAM role.
5. Create tables

```bash
$ python3 create_tables.py
```
6. Extract, Load and Transform the data from S3 bucket to Staging table and insert transformed data to dimension/fact tables.

```bash
$ python3 etl.py
```

## Sample SQL queries

Check data has been loaded successfully

```sql
SELECT * FROM songplays LIMIT 20;
```

```sql 
SELECT * FROM users LIMIT 20;
```

```sql 
SELECT * FROM songs LIMIT 20;
```
