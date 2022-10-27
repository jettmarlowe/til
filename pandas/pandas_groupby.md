
# Renaming columns in Pandas `groupby`

`groupby` in Pandas is sort of annoying compared to `group_by` in R's [dplyr](https://dplyr.tidyverse.org/reference/group_by.html).  It's harder to read, there used to be a `NamedAgg` class to include, and it defaults to a MultiIndex. 

However, as of pandas 0.25, you can [rename columns with a tuple](https://pandas.pydata.org/pandas-docs/stable/whatsnew/v0.25.0.html#groupby-aggregation-with-relabeling).  
  
The examples in the pandas [groupby documentation](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.DataFrame.groupby.html) don't show this so I often forget the syntax.  

## Example: Pandas `groupby` 
```python

animals = pd.DataFrame({'kind': ['cat', 'dog', 'cat', 'dog'],
                        'height': [9.1, 6.0, 9.5, 34.0],
                        'weight': [7.9, 7.5, 9.9, 198.0]})

animals.groupby('kind', as_index=False).agg( # use as_index=False to remove the MultiIndex
    min_height=('height', 'min'),
    max_height=('height', 'max'),
    median_weight=('weight', 'median'),
    animal_count=('kind', 'count'),
    unique_animal_type=('kind', 'nunique')
)
```


### References
* [GroupBy aggregation with relabeling](https://pandas.pydata.org/pandas-docs/stable/whatsnew/v0.25.0.html#groupby-aggregation-with-relabeling)