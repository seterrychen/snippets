# decorator sample code

## decorator with arguments

Reference: [Python - Get original function arguments in decorator](https://stackoverflow.com/questions/1010080/python-get-original-function-arguments-in-decorator)

```
def login_required(f):
    def wrapper(*args, **kw):
        args[0].client_session['test'] = True
        logged_in = 0
        if logged_in:
            return f(*args, **kw)  # Call hello
        else:
            return redirect(url_for('login'))
    return wrapper

@login_required()
def hello(request, name):
    return render_template('say_hello.html', name=name)
```
