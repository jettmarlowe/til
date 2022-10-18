# Debugging in Python

Python tries to help when an error occurs by info vomiting on you.  
A lot of text and code comes out.  
This is called a traceback.   
The traceback can be read from the bottom to top.   
The primary reason for the error is at the very bottom of the traceback.  

## In a notebook
```python
%debug 
  
# type u and enter will take you one step up in the traceback
# type d and enter will take you down one step
# type p to print any value you want

# inspect variables, size of variables, type of variables to get more info on the issue

# type q and enter to quit

```

## Why does the traceback show the exception at the bottom?
Having the exception at the bottom of the traceback makes it easier to read in case you are using a terminal since this is last line you see. 

## Alternatives
* For a small section of code, you can just use ```print()``` to inspect your code.
* Python also has a [```logging``` library](https://docs.python.org/3/library/logging.html)
  
  
### Resources
* [What is a Python Traceback?](https://realpython.com/python-traceback/)
* [pdb, the Python Debugger](https://docs.python.org/3/library/pdb.html)