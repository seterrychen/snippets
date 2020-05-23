## Install
```
pip install flask
```

## Usage
### Tutorial
* [Flask for Beginners Tutorial - Learn Flask in 40 Minutes (2019)](https://www.youtube.com/watch?v=EnJKHVEzHFw)
* [Using Flask & MongoDB to add pagination](https://harishvc.com/2015/04/15/pagination-flask-mongodb/)

### [Project Layout](https://flask.palletsprojects.com/en/1.1.x/tutorial/layout/)
```
/home/user/Projects/flask-tutorial
├── flaskr/
│   ├── __init__.py
│   ├── db.py
│   ├── schema.sql
│   ├── auth.py
│   ├── blog.py
│   ├── templates/
│   │   ├── base.html
│   │   ├── auth/
│   │   │   ├── login.html
│   │   │   └── register.html
│   │   └── blog/
│   │       ├── create.html
│   │       ├── index.html
│   │       └── update.html
│   └── static/
│       └── style.css
├── tests/
│   ├── conftest.py
│   ├── data.sql
│   ├── test_factory.py
│   ├── test_db.py
│   ├── test_auth.py
│   └── test_blog.py
├── venv/
├── setup.py
└── MANIFEST.in
```

### example code
```
from flask import Flask
from flask import abort
from flask import request
from flask import jsonify


app = Flask(__name__)
IP="127.0.0.1"


@app.route('/ccc', methods=['POST'])
def do_something():
    data = request.get_json()
    name = data['name']
    if name != 'terry':
        abort(403)
    return jsonify({'status': 'ok'})


if __name__ == '__main__':
    app.run(host=IP)
```

### get parameter
```
from flask import request

@app.route('/my-route')
def my_route():
  page = request.args.get('page', default = 1, type = int)
  filter = request.args.get('filter', default = '*', type = str)
```
```
/my-route                       -> page:  1  filter: '*'
/my-route?page=10&filter=test   -> page: 10  filter: 'test'
```

### get parameter of route path
```
from flask import request

@app.route('/login/<username>', methods=['GET'])
def login(username):
    print(username)
```
