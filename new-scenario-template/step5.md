We are now heading to step number 5. In this step, you will learn how to use filter methods in pyspark and pandas/python.

# TXT File Data

First of all, it might be useful to count rows which for instance contain a certain word. The next example shows how to count rows that mention at least one `Erl-King`.

```python
word_filter = spark_txt.value.contains("Erl-King")
spark_txt_filtered = spark_txt.filter(word_filter)
```{{execute}}

The line above creates a new dataframe out of the old one. A filter was applied to only select certain rows that contain the word `Erl-King` ("Interactive Analysis with the Spark Shell", n.d.). Now, use the `count()` function on the new dataframe to see the results.

`spark_txt_filtered.count()`{{execute}}

However, it can get a bit more difficult when it comes to filtering in python, so we need another strategy here which is called list comprehension (Petty, 2021). This is a powerful method in python that is used to carry out expressions on items in a list. Let's say we want to filter our list by the word `Erl-King` and then count the matching items just like above. This can be done like the following:

```python
python_txt_filtered = [row for row in python_txt if "Erl-King" in row]
len(python_txt_filtered)
```{{execute}}

# CSV File Data

This section shows how to separate dataframes by missing and non-missing values.

Based on the `info()` output earlier, we have seen that there are some missing values in several columns. Let's go ahead and filter out all rows that dont have missing values in the columns `intermediate-region` and `intermediate-region-code`.

```python
region_filter = spark_csv['intermediate-region'].isNull() & spark_csv['intermediate-region-code'].isNull()
spark_csv_filtered = spark_csv.filter(region_filter)
```{{execute}}

A new filter `region_filter` was set up and applied on the dataframe. The new dataframe should now contain all rows from the old one that dont have any non-null values in both of those certain columns. 

`spark_csv_filtered.show()`{{execute}}

Calling `show()` verifies that.

However, the filtering approach in python is a bit different: A filter is basically an expression which is a boolean value that is set into the dataframe. The idea is that each row in the dataframe shall be checked whether it matches the filter or not.

```python
region_filter = python_csv['intermediate-region'].isnull() & python_csv['intermediate-region-code'].isnull()
python_csv_filtered = python_csv[region_filter]
```{{execute}}

Last but not least, let's check if the filter has worked.

`python_csv_filtered.info()`{{execute}}

According to the terminal output, both columns in the new dataframe now have zero non-null values.