# Week 3 Homework
ATTENTION: At the end of the submission form, you will be required to include a link to your GitHub repository or other public code-hosting site. This repository should contain your code for solving the homework. If your solution includes code that is not in file format (such as SQL queries or shell commands), please include these directly in the README file of your repository.

<b><u>Important Note:</b></u> <p> For this homework we will be using the 2022 Green Taxi Trip Record Parquet Files from the New York
City Taxi Data found here: </br> https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page </br>
If you are using orchestration such as Mage, Airflow or Prefect do not load the data into Big Query using the orchestrator.</br> 
Stop with loading the files into a bucket. </br></br>
<u>NOTE:</u> You will need to use the PARQUET option files when creating an External Table</br>

<b>SETUP:</b></br>
Create an external table using the Green Taxi Trip Records Data for 2022. </br>
Create a table in BQ using the Green Taxi Trip Records for 2022 (do not partition or cluster this table). </br>
</p>

## Question 1:
Question 1: What is count of records for the 2022 Green Taxi Data??
- 65,623,481
- [x] 840,402
- 1,936,423
- 253,647

<img width="1440" alt="Screenshot 2024-02-09 at 22 54 44" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/071c65d1-74c7-4c0e-931f-0f9e28e491ee">

## Question 2:
Write a query to count the distinct number of PULocationIDs for the entire dataset on both the tables.</br> 
What is the estimated amount of data that will be read when this query is executed on the External Table and the Table?

- [x] 0 MB for the External Table and 6.41MB for the Materialized Table
- 18.82 MB for the External Table and 47.60 MB for the Materialized Table
- 0 MB for the External Table and 0MB for the Materialized Table
- 2.14 MB for the External Table and 0MB for the Materialized Table

<img width="1328" alt="Screenshot 2024-02-10 at 23 31 55" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/b69ae152-151a-41ab-a1e4-5febc730f34a">

<img width="1332" alt="Screenshot 2024-02-10 at 23 32 42" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/f74dcf6c-51bd-4611-b90a-98ee52e07cf5">


## Question 3:
How many records have a fare_amount of 0?
- 12,488
- 128,219
- 112
- [x] 1,622
<img width="1317" alt="Screenshot 2024-02-10 at 23 36 39" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/b720a017-a310-4825-83f0-49283c42d4b9">

## Question 4:
What is the best strategy to make an optimized table in Big Query if your query will always order the results by PUlocationID and filter based on lpep_pickup_datetime? (Create a new table with this strategy)
- Cluster on lpep_pickup_datetime Partition by PUlocationID
- [x] Partition by lpep_pickup_datetime  Cluster on PUlocationID
- Partition by lpep_pickup_datetime and Partition by PUlocationID
- Cluster on by lpep_pickup_datetime and Cluster on PUlocationID

## Question 5:
Write a query to retrieve the distinct PULocationID between lpep_pickup_datetime
06/01/2022 and 06/30/2022 (inclusive)</br>

Use the materialized table you created earlier in your from clause and note the estimated bytes. Now change the table in the from clause to the partitioned table you created for question 4 and note the estimated bytes processed. What are these values? </br>

Choose the answer which most closely matches.</br> 

- 22.82 MB for non-partitioned table and 647.87 MB for the partitioned table
- [x] 12.82 MB for non-partitioned table and 1.12 MB for the partitioned table
- 5.63 MB for non-partitioned table and 0 MB for the partitioned table
- 10.31 MB for non-partitioned table and 10.31 MB for the partitioned table

<img width="1329" alt="Screenshot 2024-02-10 at 23 56 56" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/99a0bba2-1884-4220-ad36-e933dc8a5d1b">

<img width="1328" alt="Screenshot 2024-02-10 at 23 57 44" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/de42e501-4171-4997-b359-d0376e7f75b6">


## Question 6: 
Where is the data stored in the External Table you created?

- Big Query
- [x] GCP Bucket
- Big Table
- Container Registry


## Question 7:
It is best practice in Big Query to always cluster your data:
- True
- [x] False


## (Bonus: Not worth points) Question 8:
No Points: Write a `SELECT count(*)` query FROM the materialized table you created. How many bytes does it estimate will be read? Why?

- [x] 0B because since the table is already partitioned and clustered it skips scanning the full table.
<img width="1328" alt="Screenshot 2024-02-11 at 00 07 09" src="https://github.com/daphnephil/Data-Engineering-Zoomcamp/assets/62921301/661a6d79-a30c-4ccd-aefc-6273637b6e09">



