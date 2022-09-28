# Download all notebooks from Tableau Server to prep for an upgrade

You can download all Tableau notebooks to your local machine in case you want to be extra careful going into an upgrade for Tableau Server.

```python
import tableauserverclient as TSC

tableau_auth = TSC.TableauAuth('username', 'password')
server = TSC.Server('http://your.tableau.url/')

with server.auth.sign_in(tableau_auth):
    for wb in TSC.Pager(server.workbooks):
        server.workbooks.download(wb.id, no_extract=True)
```
