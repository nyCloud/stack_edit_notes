# Frontend Study Notes - HTML  
Nan Yu | April 2019   
  
## JavaScript
### 1. Usage

```html
<!-- script tag -->
<head>
	<script> 
		alert("Hello JavaScript!")
	</script>
	...
</head>

<!-- external -->
<script src='test_script.js'></script>

<!-- inside html element -->
<button  type="button"  onclick="test_func()">test </button>
```
### 2. Print
JavaScript provides multiple methods to print messages
```javascript
// alert window
window.alert(...)
// write in html
document.write(...)
// write in html element
document.getElementById('test').innerHTML = 'test_msg'
// to console
console.log(...)
```

### 3. Variables & Types
#### 3.1 Variables
There are multiple ways to declare variables in JavaScript
```javascript
a = 1
// a is global

var b = 2
// if declared inside a function var can be accessible anywhere in function. Or it is a global variable

let c = 3
// let and const can only be accessible inside the block where they are declared

const d = 4
// d can not be changed
```

#### 3.2 Types
JavaScript Types
- Undefined & Null
```JavaScript
cash = null
future = undefined
```
- Number
```JavaScript
val_a = 123
val_b = 2.718
val_c = 3e8
```

- Bool
```JavaScript
cond_a = true
cond_b = false
```

- String
```JavaScript
str_a = 'Too Young'
str_b = "Too Simple"
```

- Array
```JavaScript

```

- Function
```JavaScript

```

- Object
```JavaScript
let car = {
	color: 'blue'
	type: 'camaro'
	speed: 0
	run:
	stop:
}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTMzNzI5OTMyOSwxNzkzMTY3MTM3LDExNj
M2MjE0OTksNzc1NTU1MzU0LC02NTE2MjgyMjgsMTcxODY0NDQx
NSwtMTk3ODA5MjA3OSwtOTIwMDAyODkwLDEzOTI5MTM2NTcsLT
E4MjI4MTczODVdfQ==
-->