...

# TXT File Data

...

`spark_txt_transformed.write.text("./erlking")`{{execute}}

...

```python
f = open('regions.txt', 'w')
print(*python_txt_transformed, file=f)
f.close()
```{{execute}}

# CSV File Data

...