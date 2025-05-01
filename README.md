# Microsoft Fabric - Use Delta Tables in Apache Spark

In this lab, I explored how Microsoft Fabric integrates Delta Lake functionality for managing structured and streaming data. I created both managed and external Delta tables, executed SQL queries to analyze data, and implemented streaming ingestion into a Delta table using simulated IoT input.

## 🎯 Objective

- Create a Lakehouse and upload CSV data  
- Read and explore structured data with PySpark  
- Create and compare managed and external Delta tables  
- Query Delta tables using SQL and PySpark  
- Explore table versioning and transaction history  
- Use temporary SQL views for summarization  
- Stream JSON data into Delta tables using Spark Structured Streaming  

## 🔧 What I Did

### 1. Set Up Workspace and Lakehouse  
Created a new workspace with Fabric Trial capacity. Then created a Lakehouse and uploaded the products.csv file into a new folder named `products`.

### 2. Explored Data with PySpark  
Defined a schema using Spark SQL types and loaded the products.csv file into a Spark DataFrame. Used `display()` to review the structure and content of the data.

### 3. Created Delta Tables  
Created a managed Delta table called `managed_products`, with data stored in the Lakehouse's `Tables` directory. Then created an external Delta table called `external_products`, with data stored in the `Files` section using the ABFS path.

### 4. Compared Managed vs. External Tables  
Used the `DESCRIBE FORMATTED` SQL command to compare storage locations of both table types. Verified that dropping a managed table removed both data and metadata, while dropping an external table only removed metadata.

### 5. Created Delta Table with SQL  
Used the SQL magic command to create a new Delta table called `products` pointing to the `external_products` data location. Queried this table to confirm data integrity.

### 6. Performed Updates and Explored Table History  
Executed an update operation to reduce the price of products in the 'Mountain Bikes' category by 10%. Then used `DESCRIBE HISTORY` to examine versioned transaction logs. Retrieved both the current and original versions of the table to compare.

### 7. Created a Temporary SQL View  
Used SQL to create a temporary view called `products_view` that summarizes product count and price statistics per category. Queried and sorted this view to identify top categories and price ranges.

### 8. Analyzed Data with PySpark  
Queried the temporary SQL view with PySpark, ordered results by average price, and displayed the top categories.

### 9. Simulated Streaming IoT Data  
Created a directory-based stream source and used JSON schema to simulate IoT data from devices. Created a streaming DataFrame and wrote the stream to a Delta table named `IotDeviceData`.

### 10. Queried Streaming Table  
Queried the Delta sink table using SQL. Then wrote additional data to the source and verified that it appeared in subsequent queries.

### 11. Stopped the Stream  
Gracefully stopped the Spark stream after the simulation was complete.

## 🧠 What I Learned

- The difference between managed and external Delta tables in Fabric  
- How to use schema definitions for reliable data ingestion  
- How Delta Lake enables version control and transaction history  
- How SQL magic commands simplify interaction with Delta tables  
- How to use Spark Structured Streaming with Delta sinks  
- How to simulate real-time data ingestion and perform analytics with Delta  

## 🔗 Connect with Me

👉 [Connect with me on LinkedIn](https://www.linkedin.com/in/eyilan/)
