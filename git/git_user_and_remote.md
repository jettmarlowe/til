# Who am I and how did I get here? (with Git)
When I come back to an old project on my local machine, I need to know which git account I am using and where the code lives on the remote server. 

### Who am I in git?
```bash
# Return your username and email for git in this particular directory
git config user.name 
git config user.email

# Returns:
# myusername
# myemail@emailaddress.com
```

### Where does the code live?
```bash
git remote -v 

# Returns: 
# origin  git@github.com:my_group/my_repo.git (fetch)
# origin  git@github.com:my_group/my_repo.git (push)
```

If I want to change where the code lives, I can change the remote for my repo.
```bash
git remote set-url origin git@github.com:user/repository.git

# Make sure it was updated
git remote -v

```

### Bonus: 
### After making a commit but before pushing code, make sure the user.name and user.email are set correctly
```bash
git log

# Returns the commits, author/email, and date for your repo

# CTRL + Z to exit git log
```


### References
* [Setting your Git username for a single repository](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git)
* [How to Change Git Remote Origin](https://devconnected.com/how-to-change-git-remote-origin/)