# Add a Secret to Databricks

Use the databricks CLI on your local machine to write secrets to the Databricks platform. 

You will need to create an access token in User Settings in the Databricks web console to set up the CLI locally.

### Set up the environment
```bash
conda create --name dbapi python=3.9 pip
conda activate dbapi
conda install -c conda-forge databricks-cli

# Check that databricks cli is available
databricks -v 
 
# Print out available profile info
# For new install, you will need to set this up using 'databricks configure --token'
cat ~/.databrickscfg

```


### List the available scopes
```bash
databricks secrets list-scopes --profile myprofilename
```

### List current secrets
```bash
databricks secrets list --scope dev --profile myprofilename
```

### Create a new secret
```bash
databricks secrets put --scope dev --key mytokenname --string-value mytokenhere --profile myprofilename
```