# Frontend Study Notes - HTML  
Nan Yu | April 2019   
  
## VUE
#### 1. Text & Expression Binding
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

#### 2. v-html
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

#### 3. v-bind
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

Abbr: 
```html
<!-- Origin --> 
 <a  v-bind:href="url"></a>  
<!-- Abbr -->  
<a :href="url"></a>
```
#### 4. v-if
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

#### 5. v-model

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

#### 6. v-for
To iterate a JavaScript array
```html
<div id="app">
	<ul>
		<li v-for="v in values">
			{{'i:'+ v + '  j:' + v*v}}
		</li>
	</ul>
</div>

<script>
	nums = [...Array(10).keys()]
	new Vue({
		el: '#app',
		data: function () {
			return {
				values: nums
			}
		}
	})
</script>
```

To iterate a JavaScript object
```html
<div id="app">
	<ul>
		<li v-for="(v, k) in object">
			{{ k }} | {{ v }}
		</li>
	</ul>
</div>

<script>
	new Vue({
		el: '#app',
		data: {
			object: {
				bag: '2019-01-02',
				duration: '100s',
				length: '300m'
			}
		}
	})
</script>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE0MzMxMTQ0OTQsLTMwODU2MjgzNCwtMT
U1Nzc2OTY0MiwtODgxOTkxOTQ1LDY4MDU5NjY4NSw3MTI0MzE3
ODUsLTE1MjkyNzIzMzMsLTkxODk3MzA2NSwtMTk3ODY1MzI4NC
w2OTk5MDA1ODQsMTU0NjkwMzAsLTk5MjgwNjMxNywxNzQ5MDE5
ODUsLTE1MjIxNTkwNTYsMjA0ODA3NzQ5Myw0NjEzOTkzNCwtMT
cyOTA4MjIyLC03MTAxNTgzMjZdfQ==
-->