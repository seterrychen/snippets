# Flask

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
