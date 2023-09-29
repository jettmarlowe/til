# Find the Process ID for a Port

If I'm testing an app and forget to Ctrl-C properly sometimes there are too many things listening on a port.  
I need to figure out which process IDs are related to that port.  

### Example: return the processes for port 5000
```bash
# get the PID
lsof -i :5000

# kill the PID
kill PID

# kill more forcefully
kill -9 PID

```