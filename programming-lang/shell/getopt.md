# Get command-line arguments

## Without getopt

```
while (( "$#" )); do
    case $1 in
        -c)
            shift
            option_c=$1
            ;;
        -d)
            shift
            option_d=$1
            ;;
    esac
    shift
done
```
