# Introduction to Big Data Analysis with Spark

Big Data?
- is a term used to refer to the study and applications of data sets that are too complex for traditional data-processing software.

3 V's of Big Data
1. Volume - size of the data
2. Variety - different sources and formats
3. Velocity - speed of the data

Big Data Concepts and Terminology
> Clustered Commputing - collection of resources of multiple machines
> Parallel Computing - simultaneous computation
> Distributed Computing - collection of nodes (networked computers) tha run in parallel
> Batch Processing - breaking the job into small pieces and running them on individual machines
> Real-time Processing - immediate processing of data

Big Data Processing Systems
1. Hadoop/MapReduce - Scalabale and fault tolerant framework written in Java
    - Open source
    - Batch Processing
2. Apache Spark - General Purpose and lightning fast cluster computing system
    - Open source
    - Both batch and real-time data processing

Feature of Apachec Spark Framework
- distributed cluster computing framework
- efficient in-memory computations for large data sets
- lighning fast data processing framework
- provides support for Java, Scala, Python, R and SQL

Apachec Spark Components
- Spark SQL
- MLib Maching Learning
- GraphX
- Spark Streaming
- RDD API Apache Spark Core

Spark Modes of Deployment
1. Local Mode
    - Single machine such as your laptop
    - convinient for testing, debugging and demonstration
2. Cluster Mode
    - set of pre-defined machines
    - good for production

Pyspark: Spark with Python
- Apache Spark is written in Scala
- To support Python with Spark, Apache Spark Community released PySpark
- Similar computation speed and power as scala
- PySpark APIs are similar to Pandas and Scikit-learn

What is Spark Shell?
- interactive environment for running Spark jobs
- Helpful for fast interactive prototyping 
- Spark's shell allow interacting with data on disk or memory
- 3 different Spark Shells:
    1. Spark-shell for Scala
    2. PySpark-shell for Python

PySpark Shell
- the Python-base comman line tool
- allows data scientists interface with Spark data structures
- support connectiing to a cluster

SparkContext
- is an entry point into the world of Spark
- An entry point is a way of connecting to Spark cluster
- An entry point is like a key to the house
- PySpark has a default SparkContext called sc

Inspecting SparkContext
Version: To retrieve SparkContext version (sc.version)
Python Version: To retrieve Python version of SparkContext (sc.pythonVer)
Master: UL of the cluster or "local" string to run in local mode of SparkContext (sc.master)
Load Data: sc.parallelize(list_argument)

What are anonymous functions in Python?
- Lambda functions
- very powerful and used in Python. Quite efficient with map() and filter()
- Lambda functions create functions to be called later similar to def
- It returns the functions without any name (i.e anonymous)
- Inline a function definition or to defer execution of code.