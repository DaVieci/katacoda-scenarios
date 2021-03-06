This step shows how one can read and access data from files in PySpark and Python in general.
It is divided into 2 sections which cover approaches for loading a txt file and a csv file.

# TXT File Data

In this first section, an approach will be shown how to load a txt file into the memory. First of all, let's declare a variable that holds the filename of that text file:

`text_file = "file1.txt"`{{execute}}

The text file needs to be loaded into PySpark by creating a dataframe which contains all rows of that specific file. That can be accomplished by the following line ("Interactive Analysis with the Spark Shell", n.d.):

`spark_txt = spark.read.text(text_file)`{{execute}}

On the other hand, if one wants to load the content of a text file in native python, one may use the function `readlines()`. That function gathers all lines in the file and writes them into a list. That is pretty simple to do:

```python
f = open(text_file, 'r')
python_txt = f.readlines()
```{{execute}}

# CSV File Data

This section here covers the approach of loading a csv file. So, we again start with declaring a variable again that hold the name of the csv file:

`csv_file = "file2.csv"`{{execute}}

After that, the `read` function can again be used to read a csv file (Kakarla et al., 2021, p. 38). However, some declarations need to be done beforehand. For instance, options are added to tell PySpark that there is a header in the csv file that holds the names of the columns and how each cell is separated from each other (certainly by which character, in that case by commas).

```python
spark_csv = spark.read.format("csv") \
    .option("header", "True") \
    .option("sep", ",") \
    .load(csv_file)
```{{execute}}

Moreover, loading csv files can also be pretty easy in python. The pandas library provides a function called `read_csv()` to read csv files from the disk ("Pandas Cheat Sheet", 2020). It can be used like the following:

`python_csv = pd.read_csv(csv_file)`{{execute}}
