# Migrating S3 files into a new Databricks AWS Environment

When migrating to a new Databricks AWS environment, you might need to copy over some of your existing S3 data files.  Use `dbutils` to copy the files directly in a Databricks notebook in the new environment.

Make sure the reference is to FileStore and not the S3 location.

## Works
```python
dbutils.fs.cp("s3a://old_cloud/region1-prod/123456/FileStore/tables/stats/data1.csv", "dbfs:/FileStore/tables/stats/data1.csv")
```

## Doesn't work
```python
dbutils.fs.cp("s3a://old_cloud/region1-prod/123456/FileStore/tables/stats/data1.csv", "s3a://new_cloud/region2-prod/456789/FileStore/tables/stats/data1.csv")
```


### References
* https://docs.databricks.com/dev-tools/databricks-utils.html