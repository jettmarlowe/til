# Print only a certain range of lines from a file

For testing, I want to use a narrow range of lines from a file, so I can uncover the data which is causing an issue.

This command will print out the contents of a file starting at line 5 through line 10 inclusive. 

```bash
cat -n my_file.csv | awk 'NR==5,NR==10'
```
<img src="cat.png" alt="Cat resting on a newspaper" width="200" height="200" />


## What's Happening
* `cat` is a Linux command that prints out a file. The `-n` flag tells it to include the line number in the output.  
* `my_file.csv` is the file you'd like to print out to the terminal.  
* `awk` is another ~~Linux command~~ programming language used for text manipulation. `NR` means record number ("Number Record" officially). 



### References
* https://en.wikipedia.org/wiki/AWK
* https://unix.stackexchange.com/questions/89640/how-to-run-awk-for-some-number-of-lines