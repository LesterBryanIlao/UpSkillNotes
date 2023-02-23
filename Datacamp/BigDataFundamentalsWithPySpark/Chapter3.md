# PySpark SQL & DataFrames

#### Abstracting Data with DataFrames

What are PySpark DataFrames?
- PySpark SQL is a Spark library for structured data. It provides more information about the structure of data and computation.
- PySpark Dataframe is an immutable distributed collection of data with named columns 
- Design for processing both structured (e.g relational database) and semi-structured data (e.g. JSON)
- DataFram API is a available in Python, R, Scala and Java
- DataFrames in PySpark support both SQL queries (SELECT * FROM table) and or expressions (df.select())

SparkSession - Entry pint for DataFrame API
- SparkContext - is the main entry point for creating RDDs.
- SparkSession provides a single point of entry to interact with Spark DataFrames.
- SParkSession is used to create DataFrame, register DataFrames, and execute SQL queries.
- SparkSession is available in PySpark shell as "spark".

Creating DataFrames in PySpark
> 2 Different Methods of creating DataFrames in PySpark
    1. From existing RDDs using SparkSession's createDataFrame() method
    2. From various data sources (CSV, JSON, TXT) using SparkSession's read() method.
> Schema controls the data and helps DataFrames to optimize queries
> Schema provides information about column name, type of data in the column, empty values, etc.

Create a DataFrame for RDD
> sample_df = spark.createDataFrame(sample_RDD, schema=list_of_column_names)
> type(sample_df) => pyspark.sql.dataframe.DataFrame

Create a DataFrame from reading a CSV/JSON/TXT
> df_csv = spark.read.csv("sample.csv", header=True, inferSchema=True) [same with json and txt]
> path to file and two optional parameters.

#### Operationg on DataFrames in PySpark