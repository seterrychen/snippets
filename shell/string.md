## scenario
### To detect whether string contains substring or not

bash only:

```shell=bash
string='My long string';

if [[ $string == *"My long"* ]]
then
  echo "It's there!";
fi
```

For poorer-featured shells, like busybox:

```shell=sh
string='echo "My string"'
for reqsubstr in 'o "M' 'alt' 'str';do
    if [ -z "${string##*$reqsubstr*}" ] ;then
      echo "String '$string' contain substring: '$reqsubstr'."
    else
      echo "String '$string' don't contain substring: '$reqsubstr'."
    fi
 done
```

### split string

* To Array

```
AUTH_CODE='82a8-bd7d-986d-9dc9-41f5-fc02-2c20-3175-097a-c1eb'
array=( ${AUTH_CODE//-/ } )   # using '-' to split
```

* get substring by splitting

```
${var#*SubStr}  # will drop begin of string up to first occur of `SubStr`
${var##*SubStr} # will drop begin of string up to last occur of `SubStr`
${var%SubStr*}  # will drop part of string from last occur of `SubStr` to the end
${var%%SubStr*} # will drop part of string from first occur of `SubStr` to the end
```
