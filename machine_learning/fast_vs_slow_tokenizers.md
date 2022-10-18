# Comparison of Fast vs Slow tokenizers in the Hugging Face Transformers library


|tokenizer|base library|background language|speed, batched=False|speed, batched=True|API default|offset mapping|
|---|---|---|---|---|---|---|
|fast|Tokenizers|Rust|medium|very fast|yes if available|yes|
|slow|Transformers|Python|very slow|slow|no|no|
<br>
<br>   

## So why would we even use a slow tokenizer?  
From the [Hugging Face source code](https://huggingface.co/transformers/v4.6.0/_modules/transformers/tokenization_utils_base.html), this appears to be a legacy format that is still supported.
<br>
<br>
    
### References
* [Fast tokenizers' special powers](https://huggingface.co/course/chapter6/3?fw=pt)

