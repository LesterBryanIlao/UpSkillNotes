### Big Data Fundamentals with PySpark

##### Abstarcing Data with RDDs
What is RDD?
- Resilient Distributed Datasets
- Spark's core abstraction for working with data.
- collection of data disributed across the cluster
- fundamental and backbone data type in PySpark

Decomposing / Properties of RDDs
RDDs
> Resilient: ability to withstand
> Distributed: spanning across multiple machines
> Datasets: Collection of partitioned data e.g. Arrays, Tables, Tuples, etc.

Creating RDDs. How to do it?
1. Parallelizing an existing collection of objects
    > parallelize() for creating RDDs from python lists

2. External datasets:
    - Files in HDFS
    - OBjects in Amazon S3 bucket
    - lines in a text file
    > textFile() for creating RDDs from external datasets

3. From exising RDDs
    >

Undestanding Partitioning in PySpark
- A partition is a logical division of large distributed data set.
> sc.parallelize(collection, minPartitions=N)


##### Basic RDD Transformations and Actions

Overview of PySpark Operations
> Spark Operations = Transformations + Actions
- Transformations created new RDDs
- Actions perform computation on the RDDs

RDD Transformations
- Transformations follow lazy evaluation
- map(), filter(), flatMap(), union()

RDD Actions
- operations return a value after running a computation on the RDD
- collect(), take(N), first(), count()


##### Pair RDDs in PySpark
Introduciton to pair RDDs in PySpark
- real life datasets are usually key/value pairs
- Each row is a key and maps to one or more values
- pair RDD is a special data structure to work this kine of datasets

Creating pair RDDs
> Two common ways to create pair RDDs
    - from a list of key-value tuple
    - from a regular RDD

Transformations on pair RDDs
- all regular transfomations (map(), filter(), flatMap(), union()) work on pair RDDs
- have to pass functions that operate on key value pairs rathar than on individual elements
- Examples of paired RDD Transformations:
    1. reduceByKey(func)
        - combines values with the same key
        - runs parallel operation for each key in the dataset
        - is a transformation not an action
    2. groupByKey() - group values with the same key
    3. sortByKey()
        - return an RDD that is sorted/ordered (ascending/descending) by the key 
        - sortByKey(ascending=False/True)
    4. join() - join two pair RDDs based on their key


##### Advanced RDD Actions
1. reduce(func)
    - action is used for aggregating the elements of a regular RDD
    - The function(func) should be communtative (changing order of the operands does not change the result) and assocative
    > ex. 
        RDD = sc.parallelize([1, 3, 4, 6])
        RDD.reduce(lambda x, y: x + y)
2. saveAsTextFile()
    - saves RDD into a text file inside a directory with each partition as a separate file.
    - colesce() metho can be used to sace RDD as a single text file
    > ex. RDD.coalesce(1).saveAsTextFile("tempFile")

Action Operations on pair RDDs
    - RDD actions available for PySpark Pair RDDs
    - Pair RDD actions leverage the key-value data
    - Few examples of pair RDD actions include:
        1. countByKey()
            - only available for type(K,V)
            - counts the number of elements for each key
        2. collectAsMap()
            - return the key-value pairs in the RDD as a dictionary