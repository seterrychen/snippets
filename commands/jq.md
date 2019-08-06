## Install
```
apk add jq
```


## Usage
```
$ cat filename
{"status": 123, "info": "v1"}
$ jq -Mr .status filename
123
```
