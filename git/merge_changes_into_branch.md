# Pull Changes from Main into your Branch

On your local machine:
```bash

# Download the repo
git clone git@github.com:my_username/my_repo_name.git
cd my_repo_name
 
# Switch to your branch
git checkout my-branch
 
# Get the updates and merge them
git fetch origin
git merge origin/main -m "Write your commit message here"
 
# Now you have the changes in your branch
# Finally push to publish your local commits.
git push
```