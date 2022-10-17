# What is Yanking a Version in Pip?

When trying to install a library using pip, I ran into an error:
```bash
The candidate selected for download or install is a yanked version.
```
  
## But what is a yanked version?  

[PyPI](https://pypi.org/) is the central place where people can publish and store Python packages for distribution.   
  
If a package creator wants to remove a version of files they have published (maybe they made a mistake or there is a security issue), instead of deleting the files, they can yank them.

Then PyPI will store that particular version in a hidden-away closet just like [Bertha was locked in a far away room](https://en.wikipedia.org/wiki/Bertha_Mason) at the top of Thornfield Hall in Jane Eyre. If a user specifically requests this version, they can access it with pip. However, all other users will never see this version.  

## Why not just delete instead of yanking?  
  
A bunch of people may be using your package and specific version and if you deleted the code, their projects will break. Yanking allows a way to minimize damage for all users.

### References
* [PEP 592 - Adding "Yank" Support](https://peps.python.org/pep-0592/)
* [What to do when you botch a release on PyPI](https://snarky.ca/what-to-do-when-you-botch-a-release-on-pypi/)
* [How to fix PIP yanked version warnings](https://adamj.eu/tech/2021/09/20/how-to-fix-pip-yanked-version-warnings/)


