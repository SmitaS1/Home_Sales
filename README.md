# Home_Sales
# Instructions

1. Rename the Home_Sales_starter_code.ipynb file as Home_Sales.ipynb.

2. Import the necessary PySpark SQL functions for this assignment.

3. Read the home_sales_revised.csv data in the starter code into a Spark DataFrame.

4. Create a temporary table called home_sales.

5. Answer the following questions using SparkSQL:

    * What is the average price for a four-bedroom house sold for each year? Round off your answer to two decimal places.

    * What is the average price of a home for each year the home was built, that has three bedrooms and three bathrooms? Round off your answer to two decimal places.

    * What is the average price of a home for each year the home was built, that has three bedrooms, three bathrooms, two floors, and is greater than or equal to 2,000 square feet? Round off your answer to two decimal places.

    * What is the average price of a home per "view" rating having an average home price greater than or equal to $350,000? Determine the run time for this query, and round off your answer to two decimal places.

6. Cache your temporary table home_sales.

7. Check if your temporary table is cached.

8. Using the cached data, run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

9. Partition by the "date_built" field on the formatted parquet home sales data.

10. Create a temporary table for the parquet data.

11. Run the last query that calculates the average price of a home per "view" rating having an average home price greater than or equal to $350,000. Determine the runtime and compare it to uncached runtime.

12. Uncache the home_sales temporary table.

13. Verify that the home_sales temporary table is uncached using PySpark.

14. Download your Home_Sales.ipynb file and upload it into your "Home_Sales" GitHub repository.

## Project Overview: Home Sales Data Analysis with SparkSQL

1. Importing Packages:
Imported necessary packages including findspark for initializing Spark and pyspark.sql for working with SparkSQL.

2. Creating a SparkSession:
Initialized a SparkSession using SparkSession.builder.appName("SparkSQL").getOrCreate() to establish a connection to Spark.

3. Reading Data:
Read home sales data from an AWS S3 bucket into a DataFrame using the provided URL.

4. Creating a Temporary View:
Created a temporary view named "home_sales_revised" for the DataFrame using createOrReplaceTempView() method, enabling SQL queries on the DataFrame.

5. Querying the Data:
Executed SQL queries to analyze home sales data, such as calculating the average price for a four-bedroom house sold each year and average prices based on bedrooms, bathrooms, and square footage.

6. Caching the Data:
Cached the temporary table "home_sales" using spark.catalog.cacheTable() method to enhance query performance by storing data in memory.

7. Query Runtime Comparison:
Compared the runtime of a specific query between the cached version and the version using Parquet data. Recorded start time using time.time() before executing each query and calculated the time difference to measure runtime.

8. Writing Parquet Data:
Wrote formatted home sales data to Parquet format with partitioning based on the "date_built" field using partitionBy().parquet() method.

9. Reading Parquet Data:
Read Parquet data into a DataFrame for further analysis.

10. Creating a Temporary Table for Parquet Data:
Created a temporary table named "temp_parquet" for the Parquet DataFrame using createOrReplaceTempView() method.

11. Querying Parquet Data:
Executed SQL queries on the Parquet DataFrame to filter out view ratings with an average price greater than or equal to $350,000. Measured and compared runtime to the cached version.

12. Uncaching the Temporary Table:
Uncached the temporary table "home_sales" using spark.catalog.uncacheTable() method to release memory resources.

13. Checking Caching Status:
Checked the caching status of the table "home_sales" using spark.catalog.isCached() method to confirm whether it was still cached.

Conclusion:
Demonstrated the utilization of SparkSQL for reading, querying, caching, and analyzing home sales data, offering insights into average prices based on various criteria.
