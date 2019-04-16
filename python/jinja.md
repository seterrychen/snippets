# Jinja

```
pip install jinja2
```

## [Offical docuemnt](http://jinja.pocoo.org/docs/)


## Using template file to render

```
from jinja2 import Environment, FileSystemLoader

env = Environment(loader=FileSystemLoader('folder'))
template = env.get_template('template.file')
users = [ {"name": "terry"}, {"name": "saber alter"{ ]
template.render(parameter=value)
```

template.file example(parameter is users)

```
<title>Test</title>
<ul>
{% for user in users %}
  <li><a href="{{ user['name'] }}">{{ user["name"] }}</a></li>
{% endfor %}
</ul>
```

