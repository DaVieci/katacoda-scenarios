...

# TXT File Data

...

`spark_txt_transformed.write.text("./erlking")`{{execute}}

...

```python
f = open('erlking.txt', 'w')
print(*python_txt_transformed, file=f)
f.close()
```{{execute}}

...

# CSV File Data

...

spark_csv_transformed.write.option("header","true").csv("./regions")

...

python_csv_transformed.to_csv('regions.csv')

...