# What is a Python generator?
  
A generator object can only be used once.  
The Python shortcut for a generator is to use parentheses instead of square brackets.   
  
### List example - using square brackets
```python
# Example for a list
my_list = [i for i in range(10)]

print(type(my_list))
print(my_list)
print(my_list)

# Output
# <class 'list'>
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
### vs
### Generator example - using parentheses
```python
# Example for a generator
my_generator = (i for i in range(10))

print(type(my_generator))
print(list(my_generator))
print(list(my_generator))

# Output
# <class 'generator'>
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
# []
```


## Why would you want to use a generator?
If your data is very large, a generator is helpful to do things in a for loop without loading all the data in memory first.  
Use the keyword `yield` to return a value from a generator. 


### References
* [Hugging Face Tokenizer Library - use of generator](https://huggingface.co/course/chapter6/2?fw=pt#:~:text=Using%20a%20Python%20generator)
* [Stack Overflow - yield and generators](https://stackoverflow.com/questions/231767/what-does-the-yield-keyword-do#:~:text=lot%20of%20values.-,Generators,-Generators%20are%20iterators)