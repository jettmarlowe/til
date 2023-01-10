# Databricks Runtime - what is it? 
  
A runtime system is the software environment that includes all components and packages required for the code to run.
  
In Databricks, this consists of the Spark distribution, machine learning support (if desired), and specific versions of Python packages that are required for that runtime. 
  
## Which Runtimes are available?
You can check the currently supported runtimes using the databricks CLI on your local machine.
```bash
databricks clusters spark-versions

# Output
# {
#   "versions": [
#     {
#       "key": "11.2.x-gpu-ml-scala2.12",
#       "name": "11.2 ML (includes Apache Spark 3.3.0, GPU, Scala 2.12)"
#     },
#     {
#       "key": "11.3.x-photon-scala2.12",
#       "name": "11.3 LTS Photon (includes Apache Spark 3.3.0, Scala 2.12)"
#     },
#     ...
```
  
## LTS: long-term support
Databricks supports LTS versions for two years. In Production systems, you usually will want to choose LTS versions of Databricks runtime to minimize the number of changes that occur. 
 
### References 
* [Databricks runtime releases](https://docs.databricks.com/release-notes/runtime/releases.html)