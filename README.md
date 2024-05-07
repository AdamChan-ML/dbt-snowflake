## DBT, Snowflake & Airflow Mini Project

### Data Source
As for the data source, TPC-H sample data is chosen as it is provided in Snowflake. 
As described in the TPC Benchmark™ H (TPC-H) specification:
“TPC-H is a decision support benchmark. It consists of a suite of business-oriented ad hoc queries and concurrent data modifications. The queries and the data populating the database have been chosen to have broad industry-wide relevance. This benchmark illustrates decision support systems that examine large volumes of data, execute queries with a high degree of complexity, and give answers to critical business questions.”

### Extract, Load, Transform (ELT) Pipeline:
1. Data Extraction: TPCH sample data is extracted from Snowflake.
2. Data Loading: The extracted data is load into staging table for initial processing.
3. Data Transformation: Dimension modeling technique is used to organize the transformed data into dimension tables and fact tables which ensures optimal query performance and facilitates intuitive data exploration.
4. Data Warehouse: The staging, refined and transformed data in the data models is stored in Snowflake.

### Data Modeling Technique (Dimensional Data Modeling Technique):
- Dimensional modeling is a data modeling technique used in data warehousing. It involves organizing data into dimension tables and fact tables. Dimension tables usually contain descriptive attributes (e.g., customer information, product details), while fact tables usually contain numerical measures (e.g., sales, revenue) and foreign keys linking to dimension tables.

### Setting up Snowflake
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/2df14852-046a-4ffc-9297-385e8ee2e96b)

### DBT Run
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/10c6e34d-1c43-41ea-b007-3e1b021ff79c)

### DBT Generic Test


### DBT Singular Tests


### Orchestration: Airflow DAG
- Airflow helps to orchestrate the execution of our pipeline tasks, that allows us to monitor the flow of data transformation seamlessly.
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/1f22f8a3-6032-4979-8ff7-8a0dd41a0bf0)

![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/7b15770d-5216-4c94-86cf-482b04f44bd5)


### Result Tables (in Snowflake)
#### FCT_ORDERS
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/6bd53b20-e3f4-4afc-aa6f-efcd52b71d91)

#### INT_ORDER_ITEMS
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/f562a115-890e-494f-9b6b-34418df3dd2b)

#### INT_ORDER_ITEMS_SUMMARY
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/59bc29c2-699c-403d-bcec-61b8e4577fa0)

#### STG_TPCH_LINE_ITEMS
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/ed56d7e1-4667-4e21-88c7-87b1a181e691)

#### STG_TPCH_ORDERS
![image](https://github.com/AdamChan-ML/dbt-snowflake/assets/78518992/ac34d0cf-64a6-47af-ad37-dc1a06845bd7)

