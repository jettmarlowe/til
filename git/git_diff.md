# Use git `diff` to compare two files

When setting up a background job, I needed to understand if a more recent file had any changes to it, but these files weren't part of a git repository.

When comparing two local files, use git `diff` to uncover the changes between the two documents, even if the files are not tracked in git.

```bash
git diff --color-words --no-index file1 file2
```





### References
* https://stackoverflow.com/questions/5637311/how-can-i-use-git-diff-color-words-outside-a-git-repository
* https://stackoverflow.com/questions/11561498/how-to-compare-two-files-not-in-repo-using-git