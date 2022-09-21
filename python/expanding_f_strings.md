
# Expand an F-string to include the variable name

Too lazy to write the variable name when you are printing out something from Python?

Use an equal sign `=` in an f-string to automatically expand the variable name and the evaluated variable.

```python
print(f'{log_likelihood=}')

# prints out
# log_likelihood=tensor(-38.7865)

```
This apparently works in Python 3.8+
