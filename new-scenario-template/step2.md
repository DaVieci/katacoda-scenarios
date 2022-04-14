This section shows how one can read, transform and manipulate text files in PySpark and Python in general.

Let's declare a variable that holds the filename:
`text_file = "file1.txt"`{{execute}}

## PySpark

The PySpark approach will be shown first.

The text file needs to be loaded into PySpark first by creating a dataframe which contains all rows of that specific file. That can be accomplished by the following line:
`sdf = spark.read.text(text_file)`{{execute}}

To get an idea how the content of the file looks like, it can be helpful to print out the very first line of that file by executing this:
`sdf.first()`{{execute}}

Furthermore, since it is a dataframe which holds a collection of rows, one can print out the total number of rows that the text file has. That can be done by the 'count()' function.
`sdf.count()`{{execute}}

In addition to that, it might be useful to only count rows which for instance contain a certain word. The next example shows how to count rows that has at least one 'ipsum'. 
`sdf_filtered = sdf.filter(sdf.value.contains("ipsum"))`{{execute}}

The line above creates a new dataframe. A filter was applied on the old dataframe to only select certain rows that have 'ipsum' in them. Now, use the 'count()' function on the new dataframe to see the results.
`sdf_filtered.count()`{{execute}}

## Python
