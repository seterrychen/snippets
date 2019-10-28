## Install
```
apk add jq
```


## Usage
### Get the value of a attribute
```
$ cat filename
{"status": 123, "info": "v1"}
$ jq -Mr .status filename
123
```

### Select a object with a parameter
```
$ jq -r --arg EMAILID "$EMAILID" '
        .resource[]
        | select(.username==$EMAILID) 
        | .id')
```

### Select with contains
```
$ json='[{"genre":"deep house"}, {"genre": "progressive house"}, {"genre": "dubstep"}]'
$ echo "$json" | jq -c '.[] | select(.genre | contains("house"))'
{"genre":"deep house"}
{"genre":"progressive house"}
```
