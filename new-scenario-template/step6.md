...

# TXT File Data

...

# CSV File Data

...

`spark_csv_transformed = spark_csv_filtered.groupBy('region').count()`{{execute}}

The result will look like this:

`spark_csv_transformed.show()`{{execute}}

...