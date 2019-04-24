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

### 3. Variables
```javascript
a = 1
// a is global, and can be removed
var b = 2
// b is valid within function, can not be removed
let c = 3
// c is only  
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTcxODY0NDQxNSwtMTk3ODA5MjA3OSwtOT
IwMDAyODkwLDEzOTI5MTM2NTcsLTE4MjI4MTczODVdfQ==
-->