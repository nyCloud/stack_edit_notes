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
...
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

#### 1.2. v-html
```html
<!DOCTYPE html>
...
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
```

#### 1.3. v-bind
To bind a JavaScript value or expression to html element attribute
```html
<!DOCTYPE html>
...
<style>
	.class1 {
		background: #444;
		color: #eee;
	}
</style>

<body>
	<script src="https://cdn.staticfile.org/vue/2.2.2/vue.min.js"></script>
CSSStyleDeclaration
	<div id="app">
		<label for="r1">change color</label>
		<input type="checkbox" v-model="use" id="r1">
		<br>
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

#### 1.4. v-if
```html
<div id="app">
	<p v-if="seen">now you see me!</p>
	<template v-if="ok">
		<h1>title</h1>
		<p>paragraph</p>
	</template>
</div>

<script>
	new Vue({
		el: '#app',
		data: function () {
			return {
				seen: true,
				ok: true
			}
		}
	})
</script>
```
v-else is available for the case where the condition doesn't met.

#### 1.5 v-model

```html
...
<div id="app">
	<p>{{ message }}</p>
	<input v-model="message">
</div>

<script>
	new Vue({
		el: '#app',
		data: {
			message: 'Runoob!'
		}
	})
</script>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg4MTk5MTk0NSw2ODA1OTY2ODUsNzEyND
MxNzg1LC0xNTI5MjcyMzMzLC05MTg5NzMwNjUsLTE5Nzg2NTMy
ODQsNjk5OTAwNTg0LDE1NDY5MDMwLC05OTI4MDYzMTcsMTc0OT
AxOTg1LC0xNTIyMTU5MDU2LDIwNDgwNzc0OTMsNDYxMzk5MzQs
LTE3MjkwODIyMiwtNzEwMTU4MzI2XX0=
-->