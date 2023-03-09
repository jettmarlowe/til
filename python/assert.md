# Assert is not a function

Assert can be used to generate a warning when a condition doesn't fit.  
It can be helpful for writing a mini test case right in your code.   
  
I mistakenly thought assert was a function, but it's not.   
Don't use parentheses in an assert statement otherwise it will not work correctly.  

  
A `SyntaxWarning` is generated when accidentally writing `assert` as a function.  
```python
SyntaxWarning: assertion is always true, perhaps remove parentheses?
  assert (len(df_list) == len(sheet_list), "The sheet count must be the same as the dataframe count.")
```

This should be rewritten as a statement.
```python
assert len(df_list) == len(sheet_list), "The sheet count must be the same as the dataframe count."
```

### References
* https://adamj.eu/tech/2020/06/18/why-does-python-syntaxwarning-for-assertion-is-always-true/
* https://realpython.com/python-assert-statement/
