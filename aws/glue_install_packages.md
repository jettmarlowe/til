# Installing Python packages in AWS Glue Jobs

## Specifying external Python libraries in a Glue job is different if the job is a Jupyter notebook vs a regular pyspark Glue job

### For a Jupyter Notebook in Glue
* Add directly to the Jupyter notebook code
* The syntax uses underscores
```python
%additional_python_modules paramiko

#....
import paramiko

```
  
  
### For a pyspark job in Glue
* In Job Details/Advanced Properties: Add a job parameter (argument) to the job
* Don't pip install within the Python code itself
* The syntax uses hyphens
#### Job Parameters
|Key|Value|
|---|---|
|`--additional-python-modules`  |  `paramiko`  |

#### Then within script
```python
import paramiko
```



# References
* https://repost.aws/questions/QUgbS0IF8xR_af8mmGxiVGbA/aws-glue-jupyter-notebook-additional-modules
