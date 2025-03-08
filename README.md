# Home Sales Analysis with PySpark

This project analyzes home sales data using PySpark to gain insights into pricing trends and other factors affecting the real estate market.

## Project Overview

The project performs the following tasks:

1. **Data Loading:** Loads home sales data from an AWS S3 bucket into a PySpark DataFrame.
2. **Data Exploration:** Creates a temporary view of the DataFrame to perform SQL queries.
3. **Querying:** Executes various SQL queries to answer specific questions about the data, including:
    - Average price of four-bedroom houses sold per year.
    - Average price of homes based on year built, bedrooms, bathrooms, floors, and square footage.
    - Average price of homes based on view rating.
4. **Performance Optimization:**
    - Caches the temporary table to improve query performance.
    - Compares the runtime of queries with and without caching.
5. **Data Partitioning:**
    - Partitions the data by `date_built` to improve query efficiency.
    - Saves the partitioned data as Parquet files.
    - Reads the Parquet data and creates a temporary table.
    - Compares the runtime of queries using partitioned data.
6. **Cleanup:** Uncaches the temporary table to free up resources.

## Requirements

- Google Colab or a similar environment with PySpark installed.
- Access to the home sales data in the specified AWS S3 bucket.

## Usage

1. Open the notebook in Google Colab.
2. Run the cells in order to execute the code and perform the analysis.
3. Review the output and interpretations provided in the notebook.

## Results

The project provides insights into various aspects of the home sales data, such as:
- Pricing trends based on different factors.
- Performance benefits of caching and partitioning.
- Impact of view rating on home prices.

## Conclusion

PySpark is a powerful tool for analyzing large datasets like home sales data. By leveraging its capabilities, this project provides valuable insights into the real estate market.
