# What is that?

...

# Why is it used?

...

# Setting up foundation

Please wait until you see the symbols `>>>` at the bottom on the right side of the screen before you click on the code lines below.

First of all, a Spark program begins with a SparkSession that needs to be imported from the PySpark module. 
`from pyspark.sql import SparkSession`{{execute}}

After that, that session is created by the following line:
`spark = SparkSession.builder.getOrCreate()`{{execute}}