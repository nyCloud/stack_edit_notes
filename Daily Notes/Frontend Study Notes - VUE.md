# Frontend Study Notes - HTML  
Nan Yu | April 2019   
  
## VUE
### 1.  Data Binding
#### 1.1.  Text & Expression Binding
```html
<!DOCTYPE html>
<!DOCTYPE html>
...
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
```

Then content inside {{ ... }} is still a JavaScript expression.
```html
<!DOCTYPE html>

		<div id="app">
			{{5 + 5}}<br>
			{{ ok ? 'YES' : 'NO' }}<br>
			{{ message.split('').reverse().join('') }}
			<div v-bind:id="'list-' + id">Tutorial</div>
		</div>

		<script>
			new Vue({
				el: '#app',
				data: function() {
					return {
						ok: true,
						message: 'RUNOOB',
						id : 1
					}
				}
			})
		</script>

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
```html
<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8">
		<title>Vue Test</title>
	</head>
	<style>
		.class1 {
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

#### 1.4. Expression Binding

<!--stackedit_data:
eyJoaXN0b3J5IjpbNDcwMzE1OTczLDE1NDY5MDMwLC05OTI4MD
YzMTcsMTc0OTAxOTg1LC0xNTIyMTU5MDU2LDIwNDgwNzc0OTMs
NDYxMzk5MzQsLTE3MjkwODIyMiwtNzEwMTU4MzI2XX0=
-->