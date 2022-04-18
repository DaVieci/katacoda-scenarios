## Conclusion

In conclusion, there are minor advantages and disadvantages when it comes to data handling in Spark compared to Python. While analysing data in Spark is very similar to Python/Pandas, doing some certain analytics stuff in pyspark can get a bit more complicated depending on the application or the size of the project whereas python is pretty simple and straightforward when it comes to loading data from files into a dataset or cleaning and transforming data in general. However, python (and especially pandas) was definitly not created for analysing a large amount of data that has, let's say, a few gigabytes in size since that data will get stored in the memory - which is limited in every computer. Apache Spark, on the other hand, was literally created to process big data: The data is so called "lazy-loaded". That means that an execution will not start until an action is triggered. Moreover, Spark is able to be performant and consistent by distributing the data on different nodes in a cluster, which pandas is of course not capable of. At the end, even though the data handling is pretty similar in both technologies, one would always have to go with Apache Spark when dealing with huge sizes of data.

## Further Learning

Feel free to visit the official Spark website to learn more about programming in PySpark: https://spark.apache.org/docs/latest/api/python/getting_started/index.html

## Sources

Kakarla, R., Krishnan, S. & Alla, S. (2021). Applied Data Science Using Pyspark: Learn the End-To-End Predictive Model-Building Cycle. Apress.

(n.d.). Interactive Analysis with the Spark Shell. Retrieved from https://spark.apache.org/docs/latest/quick-start.html#interactive-analysis-with-the-spark-shell

(2020). Pandas Cheat Sheet. Retrieved from https://www.dataquest.io/blog/pandas-cheat-sheet/

Petty, J. (2021). List Comprehensions in Python. Retrieved from https://www.pythonforbeginners.com/basics/list-comprehensions-in-python

(n.d.). pyspark.sql module. Retrieved from https://spark.apache.org/docs/2.1.0/api/python/pyspark.sql.html#pyspark-sql-module


Buckenhofer, A. (2022). Apache Spark. Data Warehouse lecture, 04 Tools, p. 119. DHBW Stuttgart.

Buckenhofer, A. (2022). Spark pros and cons. Data Warehouse lecture, 04 Tools, p. 128. DHBW Stuttgart.

(n.d.). Erlking Schwind. Retrieved from https://www.schubertlied.de/images/Erlking-Schwind.jpg

(n.d.). ISO country codes around the world. Retrieved from https://www.heliosdesign.com/export/sites/helios/images/glossary/iso-country-codes-around-the-world.jpg
