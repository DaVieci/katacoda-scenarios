Data transformation is done on a regular basis when working with data. This step will demonstrate a few examples how you can transform existing data to a more useful state.

# TXT File Data

In the first section, we want to remove some certain special characters from our text data. 

As stated in the introduction, pyspark provides powerful libraries that contain useful functions. Our approach for removing certain characters is to use a regex to detect and replace them. Let's go ahead and import this library right here:

`import pyspark.sql.functions as F`{{execute}}

The pyspark sql library contains a function called `regexp_replace()` that can be used to replace parts of a string with something else ("pyspark.sql module", n.d.). In that case, it will be used to remove commas, periods, exclamation marks and question marks from each row.

```python
replacer = F.regexp_replace(F.col("value"), "[,.!?]", "")
spark_txt_transformed = spark_txt_filtered.select(replacer.alias("replaced"))
```{{execute}}

A replacer was defined and applied on the dataframe. To verify the correct replacements of the characters, one can call the `show()` function again.

`spark_txt_transformed.show()`{{execute}}

As seen in the output, all rows were cleaned from the unwanted characters. 

Looking at python, the approach here is very similar as well. First of all, a regex is used to detect unwanted characters. To use regex, one needs to import the dedicated package first:

`import re`{{execute}}

Furthermore, as similar to step 5, one can use list comprehension again. However, this time it is used to apply a certain operation on list items (Petty, 2021). The `sub()` function will substitute the unwanted characters with an empty space.

`python_txt_transformed = [re.sub("[.,?!]", "", row) for row in python_txt_filtered]`{{execute}}

Let's find out if the operation above has worked:

`print(*python_txt_transformed)`{{execute}}

# CSV File Data

This section will show you how to perform data grouping which is a very common practice in data science.

Since the csv data consists of country information, one can use pyspark to group the all the countries by their regions and then count all the occurrences of each region (Kakarla et al., 2021, p. 43). That can be accomplished by the following line of code:

`spark_csv_transformed = spark_csv_filtered.groupBy('region').count()`{{execute}}

The result is again stored in a new dataframe. The result will look like this:

`spark_csv_transformed.show()`{{execute}}

Furthermore, python works nearly as the same when performing "groupby". One can again use `groupby()` to group the regions and then use `size()` to get the total number of rows in that specific group ("Pandas Cheat Sheet", 2020). 

`python_csv_transformed = python_csv_filtered.groupby('region').size().to_frame('size')`{{execute}}

Now print out the result:

`python_csv_transformed.head(20)`{{execute}}

In conclusion, if one compares the both results, one can see a difference according to the outputs. In the csv dataset, there is one row which does not have a region. However, the pyspark's `groupBy()` function was able to gather that row and to display it as a dedicated group (which is called 'null' in the earlier output). Pandas, on the other hand, seemingly ignored that row which why there are only 5 regions shown in that dataset.