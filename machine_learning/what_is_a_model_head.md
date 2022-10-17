# What is a model head?

This can be a confusing term. I couldn't find a good definition, and people don't seem to be good at explaining it.   
<br>
The full name is "model adaptation head" which helps with the understanding a bit.  
<br>
It's not akin to a _human_ head and body. Think instead of a tool (for example - a cordless drill) that has different heads (attachments) available to use for different tasks.  


<img src="https://user-images.githubusercontent.com/67592868/193310816-4203d816-d6b4-473e-bf83-c54eb879206e.png" alt='Drawing of cordless drill and attachment heads' height='250' weight='250'>



It's basically a thing you put on the model so it can handle a specific task.  
For example, the output of the Hugging Face Transformer model is sent directly to the model head to be processed.  
<br> 
This cordless drill analogy doesn't track exactly, since in certain cases there can be multiple heads on one layer, or one head feeding data to another. 
<br>


## Why it is important to structure models this way? 
So we can do transfer learning.




### References
* https://stackoverflow.com/questions/56004483/what-is-a-multi-headed-model-and-what-exactly-is-a-head-in-a-model
* https://forums.fast.ai/t/lesson-1-head-of-a-model-specifics/77262/2
* https://forums.fast.ai/t/terminology-question-head-of-neural-network/14819