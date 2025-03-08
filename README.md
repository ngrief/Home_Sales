# Home_Sales

# 🏡 Home Sales Analysis (PySpark)

This project analyzes home sales data using Apache Spark (PySpark) in Google Colab. The dataset is processed using Spark SQL to perform various queries on home prices.

## 📌 Project Overview
- Load home sales data from an AWS S3 bucket into a PySpark DataFrame.
- Create a temporary SQL table for querying.
- Analyze home prices based on different criteria.
- Optimize performance using caching and partitioning.
- Compare execution runtimes between cached, uncached, and partitioned datasets.
- Save and read Parquet formatted data for efficient storage.

## 🔧 Setup Instructions

### Install Dependencies
!apt-get update !apt-get install openjdk-11-jdk-headless -qq > /dev/null !wget -q http://www.apache.org/dist/spark/spark-3.5.3/spark-3.5.3-bin-hadoop3.tgz !tar xf spark-3.5.3-bin-hadoop3.tgz !pip install -q findspark

shell
Copy
Edit

### Start PySpark
from pyspark.sql import SparkSession import findspark

findspark.init() spark = SparkSession.builder.appName("HomeSalesAnalysis").getOrCreate()

markdown
Copy
Edit

## 🚀 Performance Optimization
- **Cached `home_sales` table**
df_cached = spark.table("home_sales") df_cached.cache() df_cached.count()

csharp
Copy
Edit
- **Partitioned by `date_built`**
df.write.partitionBy("date_built").parquet("/mnt/data/home_sales_partitioned")

graphql
Copy
Edit

## 📈 Results Summary
| Query Type       | Runtime  |
|------------------|---------|
| Uncached Query  | ~0.88s  |
| Cached Query    | ~0.0176s |
| Partitioned Query | ~0.0184s |
