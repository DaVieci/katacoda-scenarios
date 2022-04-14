# Working with text files

This section shows how one can read, transform and manipulate text files in PySpark and Python in general.

Let's declare a variable that holds the filename:
`text_file = "file1.txt"`{{execute}}

## PySpark

The PySpark approach will be shown first.

The text file needs to be loaded into PySpark first by creating a dataframe which contains all rows of that specific file. That can be accomplished by the following line:
`sdf = spark.read.text(text_file)`{{execute}}

