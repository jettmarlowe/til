# Secrets Management in Databricks Notebook

Working within a Databricks notebook, list out all the scopes and key names.  
Remove the keys that are no longer needed and rotate the remaining keys as needed.  

```python
# Iterate through all your scopes set up in Databricks and print the keys
for s in scopes:
    print('scope:', s.name)
    print('----')
    keys = dbutils.secrets.list(s.name)
    for k in keys:
        print(k.key)
    print('\n')


# Output
# scope: dev
# ----
# key1
# key2
#
# scope: stage
# key1 
# key2
#
```

### References
* [Databricks Secrets utility](https://docs.databricks.com/dev-tools/databricks-utils.html#dbutils-secrets)

