# subprocess

## Redirect subprocess output
```
import os
import subprocess

FNULL = open(os.devnull, 'w')
retcode = subprocess.call(['echo', 'foo'], stdout=FNULL, stderr=subprocess.STDOUT)
```
