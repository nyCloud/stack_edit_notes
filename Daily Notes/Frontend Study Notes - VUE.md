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
#### 1.3. Variable Binding
```html

```
#### 1.4. Element Attribute Binding
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Vue Test</title>
	</head>
	<style>
		.class1{
			background: #444;
			color: #eee;
		}
	</style>
	<body>
		<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>

		<div id="app">
			<label for="r1">change color</label><input type="checkbox" v-model="use" id="r1">
			<br><br>
			<div v-bind:class="{'class1': use}">
				v-bind:class
			</div>
		</div>

		<script>
			new Vue({
				el: '#app',
				data: function (){
					return {
						use: false
					}
				}
			});
		</script>
	</body>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTU0NjkwMzAsLTk5MjgwNjMxNywxNzQ5MD
E5ODUsLTE1MjIxNTkwNTYsMjA0ODA3NzQ5Myw0NjEzOTkzNCwt
MTcyOTA4MjIyLC03MTAxNTgzMjZdfQ==
-->