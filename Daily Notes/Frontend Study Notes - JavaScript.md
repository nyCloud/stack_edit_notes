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
```html
<!-- alert window -->
window.alert(...)
<!-- write in html -->
document.write(...)
<!-- write in html element -->
document.getElementById('test').innerHTML = 'test_msg'
<!-- to console -->
console.log(...)
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTkyMDAwMjg5MCwxMzkyOTEzNjU3LC0xOD
IyODE3Mzg1XX0=
-->