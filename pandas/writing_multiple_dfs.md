# Writing multiple dataframes using pandas.DataFrame.to_excel

## Single dataframe - use CSV
A single dataframe can be written to a CSV file using:  
```python
# In Databricks, write a dataframe to a CSV file
path = f"/dbfs/mnt/{bucket}/{directory}/{filename}"
df.to_csv(path, index=False)  
```  
  
    
## Multiple dataframes - use XLSX
If you want to write multiple dataframes, one per sheet, you can use a XLSX file.  
Note that pandas documentation says: `Multiple sheets may be written to by specifying unique sheet_name. `  
The default `sheet_name` in the function is `Sheet1`.  
  
If the list of sheet_names is omitted when writing multiple dataframes, `to_excel()` will overwrite the data, ending up with just a single `Sheet1` in the XLSX. :thinking: :unamused: 
  
In case your user forgets to provide the list of sheet names, generate some default sheet names to avoid overwriting.  

```python
# df_list contains the list dataframes to write
# sheet_list contains the unique sheet names
# If no sheet names are provided, generate them
if sheet_list is None:
    sheet_list = [f"Sheet{i}" for i in range(1, len(df_list)+1)]

    writer = pd.ExcelWriter(f"/tmp/{filename}")
    # Loop through the list of dfs and create an XLSX file, one df per sheet
    for i, val in enumerate(df_list):
    Common.to_pandas(val).to_excel(
        writer, sheet_name=sheet_list[i], index=False
    )
    writer.save()
    # Move the file from tmp on Databricks to S3
    shutil.move(
    f"/tmp/{filename}", f"/dbfs/mnt/{bucket}/{directory}/{filename}"
    )
```


### References
* [pandas.DataFrame.to_csv](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_csv.html)
* [pandas.DataFrame.to_excel](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_excel.html)