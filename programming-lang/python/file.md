# File snippets

## Read a file line by line

```
with open(filename, 'r') as f:
    for line in f:
        print(line)
```

with Line number:

```
with open(filename, 'r') as f:
    for line_no, line in enumerate(f):
        print(line_no, line)
```


## Change file permission

```
os.chmod("file", 0o755)
```
