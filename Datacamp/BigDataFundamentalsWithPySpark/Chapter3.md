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

#### Operating on DataFrames in PySpark

DataFrame operators in PySpark
- DataFrame Operations: Transform and Actions
1. DataFrame Transformations: select(), filter(), groupby(), orderby(), dropDuplicates(), and withColumnRenamed()
2. DataFrame Actions: head(), show(), count(), columns and describe()
NOTE: printSchema() is a method for any Spark dataset/dataframe and not an action

select(), show(), filter(), groupby(), orderby(), dropDuplicates(), and withColumnRenamed()
- select() tranformation subsets the columns in the DataFrame
- show() action prints the first 20 rows in the DataFrame
- filter() tranformation filters out the rows based on a condition
- grouby() operation can be used to group a variable
- orderby() operation sorts the DataFrame based on one or more columns
- dropDuplicates() removes the duplicate rows of a DataFrame
- withColumnRenamed renames a column in the DataFrame
- printSchema() operation prints the types of columns in the DataFrame
- columns operator prints the columns of a DataFrame
- describe() operation compute summary statistics of numberical columns in the DataFrame


#### Interacting with DataFrames using PySpark SQL

DataFrame API vs SQL queries
- in PySPark, you can interact with SparkSQL through DataFrame API and SQL queries
- the DataFrame API provices programmatic domain-specific language (DSL) for data
- DataFrame transformations and actions are easier to construct programmatically
- SQL queries can be concise and easier to understand and portable
- the operations on DataFrames can also be done using SQL queries

Executing SQL Queries
- The SparkSession sql() method executes SQL queries
- sql() method takes a sql statement as an argument and returns the result DataFrame
> df.createOrReplaceTempView("temp_table")
> df2 = spark.sql("SELECT field1, field2 FROM temp_table)
> df2.collect()

SQL Query to extract data
> test_df.createOrReplaceTempView("test_table")
> query = '''SELECT PRODUCT_ID FROM test_table'''
> test_product_df = spark.sql(query)
> test_product_df.show(5)


#### Data Visualization in PySpark using DataFrames

What is Data Visualization?
- is a way of representing your data in graphs or charts
- Open source plotting tools to aid visualization in Python:
    >>> Matplotlib, Seaborn, Bokeh, etc.
- Plotting graphs using PySpark DataFrames is dones using three methods:
    1. pyspark_dist_explore library
    2. toPandas()
    3. HandySpark() library

Data Visualization using Pyspark_dist_explore library
- provides quick insights into DataFrames
- Currently three functions are available - hist(), distplot(), and pandas_histogram()
> test_df = spark.read.csv("test.csv", header=True, inferSchema=True)
> test_df_age = test_df.select('Age')
> hist(test_df_age, bins=20, color='red')

Using Pandas for plotting DataFrames
- easy to create charts from pandas DataFrames
> test_df = spark.read.csv("test.csv", header=True, inferSchema=True)
> test_df_sample_pandas = test_df.toPandas()
> test_df_sample_pandas.hist('Age')

Pandas DataFrame vs PySpark DataFrame
- Pandas DataFrame are in-memory representation, single-server based structures while operations on PySpark run in parallel
- The result is generated as we apply any operation in Pandas whereas operations in PySpark DataFrame are lazy evaluation
- Pandas DataFrame are mutable while PySpark DataFrame are immutable
- Pandas API support more operations than PySpark DataFrame API

HandySpark method of visualization
- is a package designed to improve PySpark user experience
> test_df = spark.read.csv('test.csv', header=True, inferSchema=True)
> hdf.toHandy()
> hdf.cols['Age'].hist()
