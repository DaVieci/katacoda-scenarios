# PySpark RDD

...

# Pandas DataFrame

...

# Import the Packages

Please wait until you see the symbols `>>>` at the bottom on the right side of the screen before you click on the code lines below. It shows that the shell is now open and ready to run commands. This might take a while if you have skipped all the texts until this point.

First of all, a Spark program begins with a SparkSession that needs to be imported from the PySpark module. Please click on the highlighted code line below to import the pyspark package for python.

`from pyspark.sql import SparkSession`{{execute}}

Furthermore, the Pandas package also needs to be imported as well:

`import pandas as pd`{{execute}}

After that, one eventually needs to start the spark session by clicking on the following line:

`spark = SparkSession.builder.getOrCreate()`{{execute}}

Wait until the initialisation of the session is finished. You can then continue afterwards.