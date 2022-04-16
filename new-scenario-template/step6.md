...

# TXT File Data

...

# CSV File Data

...

`spark_csv_transformed = spark_csv_filtered.groupBy('region').count()`{{execute}}

The result will look like this:

`spark_csv_transformed.show()`{{execute}}

...

`python_csv_transformed = python_csv_filtered.groupby('region').size()`{{execute}}

result:

`python_csv_transformed.head(20)`{{execute}}

In conclusion, if one compares the both results, one can see a difference according to the outputs. In the csv dataset, there is one row which does not have a region. However, the pyspark's `groupBy()` function was able to gather that row and to display it as a dedicated group (which is called 'null' in the earlier output). Pandas, on the other hand, seemingly ignored that row which why there are only 5 regions shown in that dataset.