This step shows how one can read, transform and manipulate text files in PySpark and Python in general.

Let's declare a variable that holds the filename of that text file:
`text_file = "file1.txt"`{{execute}}

# PySpark

The PySpark approach will be shown in this first section.

The text file needs to be loaded into PySpark by creating a dataframe which contains all rows of that specific file. That can be accomplished by the following line:
`sdf = spark.read.text(text_file)`{{execute}}

To get an idea how the content of the file looks like, it can be helpful to print out the very first line of that file by executing this:
`sdf.first()`{{execute}}

You can see the output in the terminal on the right side. The shown value is basically the content of the first line of that file.
Furthermore, since it is a dataframe which holds a collection of rows, one can print out the total number of rows that the text file has. That can be done by the `count()` function.
`sdf.count()`{{execute}}

In addition to that, it might be useful to only count rows which for instance contain a certain word. The next example shows how to count rows that mention at least one `ipsum`. 
`sdf_filtered = sdf.filter(sdf.value.contains("ipsum"))`{{execute}}

The line above creates a new dataframe. A filter was applied on the old dataframe to only select certain rows that contain the word `ipsum`. Now, use the `count()` function on the new dataframe to see the results.
`sdf_filtered.count()`{{execute}}

# Python

This section will cover the approach of working with text files by using native python.

To load the content of the text file into python, one needs to open that file in read-mode and call the function `readlines()`. That function gathers all lines in the file and writes them into a list. That is pretty simple to do. Please click on the first code line, than on the second line below:
`f = open(text_file, 'r')`{{execute}}
`lines = f.readlines()`{{execute}}

Now let's print out the first row. Since the data is stored in a list, one only needs to print out the first element from that list:
`lines[0]`{{execute}}

The output is shown in the terminal on the right side. Unlike in PySpark, you can see that the text was printed out which is actually a string instead of a Row object.

Furthermore, to get the total amount of lines, one can simply use `len()` to print out the list size:
`len(lines)`{{execute}}

However, it can get a bit more difficult when it comes to filtering, so we need another strategy here which is called list comprehension. This is a powerful method in python that is used to carry out expressions on items in a list. Let's say we want to filter our list by the word `ipsum` and then count the matching items just like above. This can be done like the following:
`lines_filtered = [row for row in lines if "ipsum" in row]`{{execute}}
`len(lines_filtered)`{{execute}}