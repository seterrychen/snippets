# urllib

## Download file from web

```
from urllib import request
url = 'http://example.com'
with request.urlopen(url) as resp
    data = resp.read()                 # bytes object
```
