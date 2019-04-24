# Frontend Study Notes - HTML  
Nan Yu | April 2019   
  
## VUE
### 1.  Data Binding
#### 1.1.  
```html
<!DOCTYPE html>
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Vue Test</title>
		<script src="https://unpkg.com/vue/dist/vue.js"></script>
	</head>
	<body>
		<div id="app">
			<p>{{ message }}</p>
			<p>{{ value }}</p>
		</div>

		<script>
			new Vue({
				el: '#app',
				data: function () {
					return {
						message: 'hello world!',
						value: 42
					}
				}
			})
		</script>
	</body>
</html>
```

#### 1.2.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA0ODA3NzQ5Myw0NjEzOTkzNCwtMTcyOT
A4MjIyLC03MTAxNTgzMjZdfQ==
-->