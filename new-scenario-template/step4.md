...

# TXT File Data

To get an idea how the content of the file looks like, it can be helpful to print out the very first line of that file by executing this:

`spark_txt.first()`{{execute}}

You can see the output in the terminal on the right side. The shown value is basically the content of the first line of that file.

Furthermore, since it is a dataframe which holds a collection of rows, one can print out the total number of rows that the text file has. That can be done by the `count()` function.

`spark_txt.count()`{{execute}}

Now let's print out the first row by using python. Since the data is stored in a list, one only needs to print out the first element from that list:

`python_txt[0]`{{execute}}

The output is shown in the terminal on the right side. Unlike in PySpark, you can see that the text was printed out which is actually a string instead of a Row object.

Furthermore, to get the total amount of lines, one can simply use `len()` to print out the list size:

`len(python_txt)`{{execute}}

# CSV File Data

...

`spark_csv.printSchema()`{{execute}}

...

`spark_csv.show()`{{execute}}

...

`python_csv.info()`{{execute}}

...

`python_csv.head(20)`{{execute}}

...