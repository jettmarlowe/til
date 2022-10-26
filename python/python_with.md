# Grocery Shopping with the Python WITH statement

Resource management is something to think about when designing production<sup>1</sup> level code.  
  
This is more of a Computer Science concept, but since Data Science is interdisciplinary, you have to know this stuff anyway (along with stats, machine learning, data engineering, and dev-ops :relaxed:).  
  
Forgetting to close files, network connections, or database connections once you are done with them can cause memory issues.  
  
## Grocery store :green_apple: :banana: :poultry_leg: :bread:  
At the grocery store, you grab a cart to hold groceries, then go to check out. Once you are done shopping, you return your cart to the front of the store. Then others can use it.  
  
If no one returns the cart, you have to hold all your groceries in your arms, you start dropping items all over the place, your carton of eggs cracks on the floor, someone else steps in it, and chaos.   
  
## Use and return the cart using WITH  
You can use WITH as a cart to hold the stuff you are using during the operation. 
Then the cart gets automatically returned once you are done so other processes can use it. 

### Example: write to a file  
```python
with open('grocery_list.txt', mode='w') as file:
    # Open the file object
    # Call __enter__ and plan to return the file
    # Do stuff to the file
    file.write('Hot Sauce\n')
    file.write('Potatoes\n')
# __exit__ and the file gets automatically closed 
```
  
### Example: run a Gradio demo  
```python
import gradio as gr

def welcome(name):
    return f"Welcome to Gradio, {name}!"

with gr.Blocks() as demo:
    # Set up a blocks object
    # Call __enter__ and plan to return the demo object
    # Add stuff to the demo
    inp = gr.Textbox(placeholder="What is your name?")
    out = gr.Textbox()
    inp.change(welcome, inp, out)

demo.launch()
# Once done, __exit__ and the demo automatically gets closed
```

For the Gradio example, if you look at https://github.com/gradio-app/gradio/blob/main/gradio/blocks.py, you can see exactly where the `__enter__` and `__exit__` are implemented in classBlockContext



### References
* [Context Managers and Python's with Statement](https://realpython.com/python-with-statement/)
* [Python Magic Methods and Context Managers](https://rszalski.github.io/magicmethods/#context)
* [Gradio Blocks and Event Listeners](https://gradio.app/blocks_and_event_listeners/#event-listeners-and-interactivity)

### Footnotes
1. [What makes "production code"?](https://stackoverflow.com/questions/52009044/what-makes-a-production-code)