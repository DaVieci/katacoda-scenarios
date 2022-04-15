...

# TXT File Data

In addition to that, it might be useful to only count rows which for instance contain a certain word. The next example shows how to count rows that mention at least one `ipsum`. 
```python
word_filter = spark_txt.value.contains("ipsum")
spark_txt_filtered = spark_txt.filter(word_filter)
```{{execute}}

The line above creates a new dataframe. A filter was applied on the old dataframe to only select certain rows that contain the word `ipsum`. Now, use the `count()` function on the new dataframe to see the results.
`spark_txt_filtered.count()`{{execute}}

However, it can get a bit more difficult when it comes to filtering in python, so we need another strategy here which is called list comprehension. This is a powerful method in python that is used to carry out expressions on items in a list. Let's say we want to filter our list by the word `ipsum` and then count the matching items just like above. This can be done like the following:
```python
python_txt_filtered = [row for row in python_txt if "ipsum" in row]
len(python_txt_filtered)
```{{execute}}

# CSV File Data

based on info() we have seen that there are some missing values
filter all rows that dont have missing values in intermediate-region and intermediate-region-code
```python
region_filter = spark_csv['intermediate-region'].isNull() & spark_csv['intermediate-region-code'].isNull()
spark_csv_filtered = spark_csv.filter(region_filter)
```{{execute}}

new dataframe should contain all rows that dont have any values in intermediate-region and intermediate-region-code
`spark_csv_filtered.show()`{{execute}}

as seen in the console output: dataframe was filtered successfully

now in python: filter is used as an expression which is a boolean value, filter is then set into the dataframe, each row in the dataframe will be checked whether it matches the filter or not.
```python
region_filter = python_csv['intermediate-region'].isnull() & python_csv['intermediate-region-code'].isnull()
python_csv_filtered = python_csv[region_filter]
```{{execute}}

now we check if the both columns in the dataframe still contain values.
`python_csv_filtered.info()`{{execute}}

both columns now have zero non-null values which is correct