Now you have reached the final step. When working with data, you might want to save that data to a file in the later phase. Some examples will be shown here.

# TXT File Data

The text data is now ready to be saved to a file. In contrast to the read operation in pyspark ("Interactive Analysis with the Spark Shell", n.d.), one can execute a write operation as well to save a dataframe to a file.

`spark_txt_transformed.write.text("./erlking")`{{execute}}

This operation has created a new folder in the same directory called `erlking` where one can find a txt file containing the data from `spark_txt_transformed`.

Python, on the other hand, provides a lot of different methods to save data to a file. The more convinient one would be to print out the content of the list `python_txt_transformed` into a file (instead of printing it on the terminal). This can be done by defining a new file with "open":

```python
f = open('erlking.txt', 'w')
print(*python_txt_transformed, file=f)
f.close()
```{{execute}}

The operation above has created a new text file called `erlking.txt` in the same directory.

# CSV File Data

When it comes to saving dataframes to csv files in pyspark, one can declare additional options to the operation such as defining the existence of a header. Other than that, it is a pretty similar approach like above.

`spark_csv_transformed.write.option("header","true").csv("./regions")`{{execute}}

Pyspark will again create an extra directory again called `regions` that holds a txt file with the data.

The python way, on the other hand, is also simple and straightforward. Pandas provides a function called `to_csv()` to save dataframes to csv files ("Pandas Cheat Sheet", 2020).

`python_csv_transformed.to_csv('regions.csv')`{{execute}}