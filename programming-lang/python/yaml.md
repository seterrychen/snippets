# PyYAML

```
pip install pyyaml
```

## [Document](https://pyyaml.org/wiki/PyYAMLDocumentation)

## Load yaml file

```
import yaml

with open("example.yaml", 'r') as stream:
    try:
        print(yaml.load(stream))
    except yaml.YAMLError as exc:
        print(exc)
```
