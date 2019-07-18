## Install

```
apk add rsync
```


## Usage

### local, general usage
```
rsync -avh /src /dst
-a: achive mode; equals -rlptgoD
    This is equivalent to -rlptgoD. It is a quick way of saying you want recursion and
    want to preserve almost everything.
-v, --verbose
-h, --human-readable
```

### with no permission, no owner, no group
```
rsync -a --no-perms --no-owner --no-group /src /dst
--no-OPTION: turn off one or more implied options 
```
