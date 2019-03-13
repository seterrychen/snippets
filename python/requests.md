# requests

```
pip install requests
```

## [Offical docuemnt](http://docs.python-requests.org/en/master/api/)


## Get content of a url

```
img_content = requests.get(uri).content  # bytes
```

## GET method with header

```
requests.get(uri, headers={'Authorization': 'TOK:<MY_TOKEN>'})
```
