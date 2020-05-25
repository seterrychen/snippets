## Usage

### to edit files in-place instead of printing to standard output
```
$ sed -i 's/hello/world/' file
```

### insert line before the X line
```
$ # 3i means that to insert line before the third line, 
$ sed "3iwording" 
```

### to extract a predetermined range of lines from a text file
```
$ sed -n '16224,16482 p' orig-data-file
$ # -n, --quiet, --silent  suppress automatic printing of pattern space
$ # p   Print out the pattern space (to the standard output)
```

### delete line using line number
```
$ sed -i '2,8d' file
```

### Add character to the beginning of each line using sed 
```
$ sed 's/^/#/' file.txt
```
