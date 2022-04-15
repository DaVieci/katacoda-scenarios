This step shows how one can read and create data from files in PySpark and Python in general.
It is divided into 2 sections which cover approaches for loading txt and csv files.

# TXT File

In this first section, an approach will be shown how to load a txt file into the memory. First of all, let's declare a variable that holds the filename of that text file:
`text_file = "file1.txt"`{{execute}}

The text file needs to be loaded into PySpark by creating a dataframe which contains all rows of that specific file. That can be accomplished by the following line:
`spark_txt = spark.read.text(text_file)`{{execute}}

On the other hand, if one wants to load the content of a text file in native python, one may use the function `readlines()`. That function gathers all lines in the file and writes them into a list. That is pretty simple to do. Please click on the first code line, than on the second line below:
```python
f = open(text_file, 'r')
python_txt = f.readlines()
```{{execute}}

# CSV File

This section here covers the approach of loading a csv file. So, we again start with declaring a variable again that hold the name of the csv file:
`csv_file = "file2.csv"`{{execute}}

...

```python
spark_csv = spark.read.format("csv") \
    .option("header", "True") \
    .option("sep", ",") \
    .load(csv_file)
```{{execute}}

...

`python_csv = pd.read_csv(csv_file)`{{execute}}

...