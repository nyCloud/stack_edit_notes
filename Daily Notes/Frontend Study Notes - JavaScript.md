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
### 2. JavaScript Message
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
There are multiple ways to declare variables in JavaScript
```javascript
a = 1
// a is global, and can be removed
var b = 2
// if var variable is decleared inside function, it is a local variable within fuction, if not it is a global variable

let c = 3
// c is only valid within block
const d = 4
// d is only valid within block, can not be changed
```

Types suppore


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTY1MTYyODIyOCwxNzE4NjQ0NDE1LC0xOT
c4MDkyMDc5LC05MjAwMDI4OTAsMTM5MjkxMzY1NywtMTgyMjgx
NzM4NV19
-->