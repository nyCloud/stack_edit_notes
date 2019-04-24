# Frontend Study Notes - HTML  
Nan Yu | April 2019   
  
## VUE
### 1.  Data Binding
#### 1.1.  Text Binding
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

#### 1.2. Html Binding
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Vue Test</title>
		<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
	</head>
	<body>
		<div id="app">
			<div v-html="message"></div>
		</div>

		<script>
			new Vue({
				el: '#app',
				data: {
					message: '<h1>html binding</h1>'
				}
			})
		</script>
	</body>
</html>
```

#### 1.3. Element Attribute Binding

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTc0OTAxOTg1LC0xNTIyMTU5MDU2LDIwND
gwNzc0OTMsNDYxMzk5MzQsLTE3MjkwODIyMiwtNzEwMTU4MzI2
XX0=
-->