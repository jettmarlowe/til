# Using Python's staticmethod vs classmethod
  
  
## @staticmethod
### What is it?
* It is a decorator that can be used to help organize your code.
* You can use it when your function doesn't need to know or remember anything about the class but logically the function makes sense to store within that class.
### Should I use it?
* No - don't use it unless absolutely necessary. 
* It still exists for legacy reasons but apparently was [initially a mistake](https://mail.python.org/pipermail/python-ideas/2016-July/041189.html).
  
    
## @classmethod
### What is it?
* It is a decorator that is associated with a class. 
* You call the function from the class instead of the class **instance**.
* So instead of passing in `self` as the first argument , `cls` is passed in.
### Should I use it?
* Sure, you can use it if helps make your code easier to understand.
* However, there may be other ways to organize your code. 
  
    
## I'm confused :unamused:
Based on the many Stack Overflow questions, developer blog posts, and from talking to colleagues, this is confusing to many people.  
Don't worry about it - use `@classmethod` when necessary and spend your time learning other things about Python instead.



### References
* https://google.github.io/styleguide/pyguide.html#217-function-and-method-decorators
* https://stackoverflow.com/questions/136097/difference-between-staticmethod-and-classmethod