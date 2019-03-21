# Encodin

## URL string into normal string

ex: '%CE%B1%CE%BB%20' -> 'αλ'

```
from urllib.parse import unquote
unquote('%CE%B1%CE%BB%20')
```
