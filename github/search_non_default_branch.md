# Searching code in a non-default Github branch

Only the default branch is indexed in Github, so if you need to search for code in another specific branch you'll need to use a workaround.

```bash
# Clone the repo locally
git clone git@github.com:myproject/myrepo.git
cd myrepo

# Find the branch you want to search and download it locally
git fetch
git switch the-branch-i-want-to-search

# Search the branch
git grep 'search_term' 
```



### References
https://stackoverflow.com/questions/31891733/searching-code-in-a-specific-github-branch
