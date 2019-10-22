# Loop syntax

## for
```
for i in $(seq 1 5); do
    echo $i
done
```

```
for ((i = 1; i <= 5; i++)); do
  echo $i
done
```


## until
```
i = 1 
until [ $i -gt 5 ]; do
   echo $i
   ((i++))
done
```
