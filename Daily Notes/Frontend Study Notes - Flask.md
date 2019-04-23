# Frontend Study Notes - HTML  
Nan Yu | April 2019   

## Flask

### 1. Flask App
```python
from flask import Flask

# Create flask app
flask_app = Flask(__name__)

# Debug mode
app.debug = True  # or False

# Run app (usually last function to call)
app.run(host, port, debug)
'''
	- host: '127.0.0.1' local host(default)
			'0.0.0.0' external visible
	- port: port to run flask app
	- debug: debug mode
'''
```

### 2. Flask Route
#### 2.1 Basic Usage
```python
from flask import Flask  
app = Flask(__name__)  
  
@app.route('/')  
def index_page():  
    return '<h1>Hello Flask</h1>'  
  
@app.route('/add_one/<int:val>')  
def add_one(val):  
    return 'Add one result = {}'.format(val + 1)  
  
@app.route('/add_nums/<int:val_a>_<int:val_b>')  
def add_nums(val_a, val_b):  
    return 'Add nums result = {}'.format(val_a + val_b)  
  
if __name__ == '__main__':  
    app.run()
```

Then you can try to visit urls like following in your browser: 
- Run: [http://127.0.0.1:5000/add_nums/1_2](http://127.0.0.1:5000/add_nums/1_2)
- Return: Add nums result = 3

Converters:
- int: int value
- float: float value
- path: path value (include '/')

#### 2.2 Url For
Also, flask provides method to generate URL for specific function:
```python
if __name__ == '__main__':  
    with app.test_request_context():  
        print url_for('index_page')  
        print url_for('add_one', val=1)  
        print url_for('add_nums', val_a=1, val_b=2)  
    app.run()
```
You'll get result as:
```
/
/add_one/1
/add_nums/1_2
```

#### 2.3 HTTP Methods
Python
```python
from collections import deque  
from flask import Flask, url_for, request, redirect  
app = Flask(__name__)  
  
visit_history = deque(maxlen=3)  
  
@app.route('/')  
def index():  
    return '<h1>index page</h1>'  
  
  
@app.route('/success/<name>')  
def success(name):  
    return 'welcome {}\n History = {}'.format(name, visit_history)  
  
  
@app.route('/login', methods=['POST', 'GET'])  
def login():  
    print 'URL = {}'.format(request.path)  
    print 'Request method = {}'.format(request.method)  
  
    if request.method == 'POST':  
        user = request.form['name']  
        pwd = request.form['password']  
    else:  
        user = request.args.get('name')  
        pwd = request.args.get('password')  
  
    visit_history.append((user, pwd))  
    print 'User name = {}\n Password = {}'.format(user, pwd)  
    return redirect(url_for('success', name=user))  
  
  
if __name__ == '__main__':  
    app.run()
```

Html
```html
<html>  
	<head>  
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>  
		<title>Flask HTTP Methods</title>  
	</head>  
	
	<body>
		<form action = "http://localhost:5000/login" method = "get"> <!-- or post -->  
			<p>name:</p>  
			<p><input type = "text" name = "name" value=""/></p>  
			<p>password:</p>  
			<p><input type = "text" name = "password" value=""/></p>  
			<p><input type = "submit" value = "submit" /></p>  
		</form> 
	</body>
</html>
```
### 3. Cookies & Sessions
#### 3.1. Cookies
```python
from flask import Flask, render_template, request, make_response, redirect, url_for  
app = Flask(__name__, template_folder='templates')  
  
  
@app.route('/')  
def index():  
    return redirect(url_for('static', filename='index.html'))  
  
  
@app.route('/set_cookie', methods=['POST', 'GET'])  
def set_cookie():  
    if request.method == 'POST':  
        user = request.form['name']  
        resp = make_response(render_template('read_cookie.html'))  
        resp.set_cookie('userID', user)  
        return resp  
  
  
@app.route('/get_cookie')  
def get_cookie():  
    name = request.cookies.get('userID')  
    return '<h1>welcome, '+name+'</h1>'  
  
  
if __name__ == '__main__':  
    app.run(debug=True)
```

index.html
```html
<html>  
	<head>  
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />  
		<title>Flask Cookies</title>  
	</head>  
	
	<body>
		<form action = "/set_cookie" method = "POST">  
			<p><h3>Enter userID</h3></p>  
			<p><input type = 'text' name = 'name'/></p>  
			<p><input type = 'submit' value = 'login'/></p>  
		</form>  
	</body>
</html>
```
read_cookie.html
```html
<p1> Cookie for You !</p1>  
<a href='/get_cookie'> Get Cookie </a>>
```

#### 3.2. Session
```python
import os  
import time  
from flask import Flask, session, url_for, request, redirect  
  
app = Flask(__name__)  
app_key = str(os.urandom(32))  
app.secret_key = app_key  
  
@app.route('/')  
def index():  
    print 'Current Sessions = {}'.format(session)  
  
    if 'username' in session:  
        valid_until = session['valid_until']  
        if time.time() < valid_until:  
            return 'Logged in as {} !'.format(session['username'])  
        else:  
            print 'Last Session Expired!'  
  session.pop('username', None)  
            session.pop('valid_until', None)  
  
    return redirect(url_for('static', filename='login.html'))  
  
@app.route('/success/<name>')  
def success(name):  
    return redirect(url_for('index'))  
  
@app.route('/login', methods=['POST', 'GET'])  
def login():  
  
    if request.method == 'POST':  
        user = request.form['name']  
        pwd = request.form['password']  
    elif request.method == 'GET':  
        user = request.args.get('name')  
        pwd = request.args.get('password')  
    else:  
        return redirect(url_for('static', filename='login.html'))  
  
    session['username'] = user  
    session['valid_until'] = time.time() + 10  
  
  print 'User name = {}\n Password = {}'.format(user, pwd)  
    return redirect(url_for('success', name=user))  
  
if __name__ == '__main__':  
    app.run()
```
login.html
```html
<html>  
	<head>  
		 <meta http-equiv="Content-Type" content="text/html; charset=utf-8"/>  
		 <title>Flask HTTP Methods</title>  
	</head>  
	<body> 
		<form action = "http://localhost:5000/login" method = 'post'>  
		<p>name:</p>  
		<p><input type = "text" name = "name" value=""/></p>  
		<p>password:</p>  
		<p><input type = "text" name = "password" value=""/></p>  
		<p><input type = "submit" value = "submit" /></p>  
		</form> 
	</body>
 </html>
 ```

### 4. File
```python
import os  
from werkzeug import secure_filename  
from flask import Flask, render_template, request, url_for, redirect  
app = Flask(__name__)  
  
# print os.path.dirname()  
  
base_path = os.path.join(os.path.dirname(__file__), 'upload')  
print base_path  
  
@app.route('/')  
def index():  
    return redirect(url_for('static', filename='upload.html'))  
  
@app.route('/upload', methods=['GET', 'POST'])  
def upload_file():  
    if request.method == 'POST':  
        f = request.files['file']  
        f.save(os.path.join(base_path, secure_filename(f.filename)))  
        return 'file uploaded successfully'  
  else:  
        return render_template('upload.html')  
  
if __name__ == '__main__':  
    app.run(debug=True)
```
upload.html
```html
<html>  
	<head>  
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />  
		<title>Flask Test</title>  
	</head>  
	
	<body>  
		<form action = "http://localhost:5000/upload" method = "POST"  
		 enctype = "multipart/form-data">  
		<input type = "file" name = "file" />  
		<input type = "submit" value="sibmit"/>  
		</form>  
	</body>
</html>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgzNzk2NTc1MV19
-->