In the next step, we will set up the programming environment. The environment consists of python packages that need to be imported first.

# PySpark RDD

Spark provides a main abstraction called `RDD`, or `resilient distributed dataset` (Kakarla et al., 2021, p. 33). These datasets are basically a collection of our stored data and are quite flexible when it comes to handling structured, semi-structured, and unstructured data. They can also be distributed across nodes in a cluster. RDDs can always be changed to a DataFrame if a schema can be defined.

# Pandas DataFrame

In contrast to PySpark, we are going to use a python library called `Pandas`. This package provides fast and flexible data structures to work with data. Even though native python also provides data structures that are capable of holding different kinds of data, it can get quite challenging when it comes to cleaning, viewing or transforming data. That is why we use an external python package like pandas to make the data handling more convenient in python.

# Import the Packages

Please wait until you see the symbols `>>>` at the bottom on the right side of the screen before you click on the code lines below. It shows that the shell is now open and ready to run commands. This might take a while if you have skipped all the texts until this point.

First of all, a Spark program begins with a SparkSession that needs to be imported from the PySpark module. Please click on the highlighted code line below to import the pyspark package for python.

`from pyspark.sql import SparkSession`{{execute}}

Furthermore, the Pandas package also needs to be imported as well:

`import pandas as pd`{{execute}}

After that, one eventually needs to start the spark session by clicking on the following line:

`spark = SparkSession.builder.getOrCreate()`{{execute}}

Wait until the initialisation of the session is finished. You can then continue afterwards.