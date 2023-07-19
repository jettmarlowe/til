# Return all the tables in a schema along with the size of each

## Why?
I'm doing some testing in Databricks and I want to find the smallest table to test with so time isn't wasted waiting for the code to run.

## `get_table_sizes` function
```python
import pandas as pd

def get_table_sizes(schema):
    # Return the list of tables in the schema
    table_list = spark.catalog.listTables(schema)

    # Loop through each table and get the size
    table_sizes = []
    spark.sql(f"USE SCHEMA {schema};")
    for table in table_list:
        size = spark.table(table.name).count()
        table_sizes.append((table.name, size))

    return pd.DataFrame(table_sizes, columns=['table', 'size']).sort_values('size')
```


# References
* https://community.databricks.com/t5/data-engineering/get-total-size-of-data-in-a-catalog-and-schema-in-unity-catalog/m-p/10246