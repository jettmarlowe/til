# Using a conda environment with Jupyter Notebook

If you'd like to use jupyter notebook with your conda environment, there is an extra step to take.  
Create a kernel for the conda environment in order to use Jupyter.  

## Example conda environment
```bash
# create the environment
conda create --name mynotebook python=3.11

# activate it
conda activate mynotebook

# install ipykernel for jupyter notebook
conda install ipykernel

# install other required packages
conda install -c conda-forge openai

# create the kernel
python -m ipykernel install --user --name=mynotebook

# start jupyter notebook
jupyter notebook
```
## Set the kernel in Jupyter Notebook
Kernel - not selected yet  
<img src="kernel_not_set.png" alt="Kernel is not yet set" />

Kernel - set to created kernel  
<img src="kernel_set.png" alt="Kernel has been selected" />
  
## ModuleNotFoundError
If the kernel isn't created or selected in Jupyter, a `ModuleNotFoundError` will occur.

  
    

## Clean up environment
When done, remove the environment.
```bash
conda deactivate
conda remove --name mynotebook --all
```
  

      
### References
* https://docs.conda.io/projects/conda/en/latest/_downloads/843d9e0198f2a193a3484886fa28163c/conda-cheatsheet.pdf