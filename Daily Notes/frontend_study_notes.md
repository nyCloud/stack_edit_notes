# Frontend Study Notes  
Nan Yu | April 2019   
  
## HTML  
### 1. Brief Introduction
```html
<!DOCTYPE  html>  
<html>  
	<head> 
		<meta  charset="utf-8">  
		<title>HTML Introduction</title>  
	</head>
	  
	<body>  
		<h1>A title</h1>  
		<p>A paragraph</p>  
	</body>  

</html>
```
html: basic root element
head: meta data
body: visible content


### 1.1 Elements in Head
```html
<head>
	<!-- link css file -->
	<link  rel="stylesheet"  type="text/css"  href="mystyle.css">
	
	<!-- inner css format -->
	<style  type="text/css"> 
		body {background-color:yellow} 
		p {color:blue}  
	</style>
	
	<!-- javascripts -->
	<script> ... </script>
</head>
```

### 2.  HTML Elements

#### 2.1 Heading
```html
<h1> Heading is labeled from h1 to h6 </h1>
```

#### 2.2 Paragraph
```html
<p> This is a paragraph </p>

<!-- bold & italic -->
<p> <b>bold</b> <i>italic</i> </p>

<!-- css -->
<p style='color:blue;'> blue text </p>
```

#### 2.3 Link
```html
<a href='http://www.google.com'> this is a link </a>

<!-- open in a new window -->
<a href='http://www.google.com' target='_blank'> this is a link </a>
```
#### 2.4 Image
```html
<img src='/images/log.png' width='100' height='100' />

<!-- alternative source or fail prompt -->
<img src='/logo.png' alt='/fail.png'>


```

#### 2.5 Table
```html
<table  border="1">  
	<tr>  
		<th>Header 1</th>  
		<th>Header 2</th>  
	</tr>
	
	<tr>  
		<td>row 1, cell 1</td>  
		<td>row 1, cell 2</td>  
	</tr>  
	
	<tr>  
		<td>row 2, cell 1</td>  
		<td>row 2, cell 2</td>  
	</tr>  
</table>
```

#### 2.6 List
```html
<!-- unordered -->
<ul>
	<li>Apple</li>
	<li>Banana</li>
</ul>

<!-- ordered -->
<ol>
	<li>Apple</li>
	<li>Banana</li>
</ol>

<!-- self defined -->
<dl>
	<dt>Apple</dt>
		<dd>-Sweet</dd>
		<dd>-Sour</dd>
<dl>
```

#### 2.7 Div
```html
<div id="menu1" style="background-color:#FFD700;height:100px;width:10%;float:left;margin:auto;">
B1
</div>

<div id="menu2" style="background-color:#FFD700;height:100px;width:10%;float:right;margin:auto;">
B2
</div>
	
<div id="content" style="background-color:#EEEEEE;height:100px;width:80%;float:left;margin:auto;">
C</div>

<div id="footer" style="background-color:#0099CC;clear:both;text-align:center;">
D</div>

```

#### 2.8 Form
```html
<form method="get">
  <input list="browsers" name="browser">
  <datalist id="browsers">
    <option value="Internet Explorer">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
  <input type="submit">
</form>
```

#### 2.X Others
```html
<br> <!-- change line -->
<hr> <!-- split line -->
```
### 3. HTML Attributes
* class: class name for html element
* id: unique id for html element
* style: assign inline style

## CSS  
  
## Java Script  
  
## Vue  


## MongoDB
  
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

```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTIxMzM3OTg0LC02MjYwNDIxNCwtMzI2OD
A3MDg2LDMwMjEzMjA2NCwzMTQ1NDQ4MDgsLTQzMTYyNzAyMiwy
NTEzMDkxNTYsLTE2MDg4MTE3ODAsODA0ODMzNzgwLDE3MzAzOD
AwNjYsMTk2Njc3MTE2MiwtNTA3MjkyMzU5LDExMDY3OTkxOSw3
MDc3NTU0ODIsMTMzMzYwNTIwMCwzNDU0NTk0NzksMTk0NzE2NT
QyOF19
-->