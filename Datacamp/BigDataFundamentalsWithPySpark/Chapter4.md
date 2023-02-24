# Machine Learning with PySpark MLlib

What is PySpark MLlib?
- MLlib is a component of Apache Spark for machine learning
- Various tools provided by MLlib include:
    1. ML Algorithms: collaborative filtering, classification, and clustering
    2. Featurization: feature extraction, transformation, dimensionality reduction, and selection
    3. Pipelines: tools for constructing, evaluating, and tuning ML Pipelines

Why PySpark MLlib?
- Scikit-learn is a popular Python library for data mining and machine learning
- Scickit-learn algorithms only work for small datasets on a single machine
- Spark's MLlib algorithms are designed to for parallel processing on a cluster
- Supports languages such as Scala, Java and R
- Provides a high-level API to build machine learning pipelines

PySpark MLlib Algorithms
1. Classification (Binary and Multiclass) and Regression: Linear SVMs, logistic regression, decision trees, random forests, gradient-boosted trees, naive Bayes, linear least squares, Lasso, ridge regression, isotonic regression.
2. Collaborative Filtering: Alternating Least Squares (ALS)
3. Clustering: K-Means, Gaussian mixture, Bisecting K-means and Streaming K-Means

Three C's of Machine Learning in PySpark MLlib
1. Collaborative Filtering (Recommender engines): Produce recommendations
2. Classification: Identifying to which of a set of categories a new observation
3. Clustering: Groups data based on similar characteristics.

PySpark MLlib imports
> pyspark.mllib.recommendation: from pyspark.mllib.recommendation import ALS
> pyspark.mllib.classification: from pyspark.mllib.classification import LogisticRegressionWithLBFGS