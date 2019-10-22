# pathlib

Requirement: Python 3.5+


## Recursively creates the directory and does not raise an exception

```
import pathlib
pathlib.Path('/my/directory').mkdir(parents=True, exist_ok=True) 
```
