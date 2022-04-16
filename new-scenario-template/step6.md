...

# TXT File Data

...

`import pyspark.sql.functions as F`{{execute}}

...

```python
replacer = F.regexp_replace(F.col("value"), "[,.!?]", "")
spark_txt_transformed = spark_txt_filtered.select("value", replacer.alias("replaced"))
```{{execute}}

...

`spark_txt_transformed.show()`{{execute}}

...

`spark_txt_transformed = spark_txt_transformed.drop("value")`{{execute}}

...

`import re`{{execute}}

...

`python_txt_transformed = [re.sub("[.,?!]", "", row) for row in python_txt_filtered]`{{execute}}

...

`print(*python_txt_transformed)`{{execute}}

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