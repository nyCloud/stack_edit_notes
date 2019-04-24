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
#### 3.2.1 Undefined & Null
```JavaScript
cash = null
future = undefined
```

#### 3.2.2 Number
```JavaScript
val_a = 123
val_b = 2.718
val_c = 3e8
```

#### 3.2.3 Bool
```JavaScript
cond_a = true
cond_b = false
```

#### 3.2.4 String
```JavaScript
str_a = 'Too Young'
str_b = "Too Simple"
console.log(str_a[0]) // You will get 'T'
console.log(a.concat(b))  // not in-place

// get length
str_a.length
```

#### 3.2.4.1 RE
REs are also supported in JavaScript
-- format '/body/modifier(optional)'
-- body

			^: start loc
			$: end loc
			[abc]: character
			[0-9]: number
			(x|y): x & y split by |
			\d: number
			\s: includes ' ', '\t', '\n'
			\b: space between words
			n+: at least one occurance
			n*: at least zero occurance
			n?: zero or one occurance

--modifiers

		i: ignore capital & small
		g: global matching
		m: multiline matching

```JavaScript
//Some tests
re_num = /^[0-9]+$/
console.log(re_num.test('1234')
console.log(re_num.test('1234a')
console.log(re_num.exec('1234')
console.log(re_num.exec('1234a')

re_whitespace = /\s+/
console.log('a aa aaa'.split(re_whitespace))
// -> ['a', 'aa', 'aaa']
```


####  3.2.5 Array
```JavaScript
let a = [1, 2]  
let b = ['a', 'b', 'c', 'd', 'e']  
let c = [1, 2, 'apple', 4]  
console.log(a)  
console.log(b)  
console.log(c)  
console.log(c[2])  
  
// Push, pop & concat
a.push(3)  
console.log(a)  

console.log('pop')  
console.log(a.pop())  
console.log(a.pop())  
console.log(a.pop()) 

d = a.concat(b)  
console.log(a)  
console.log(d)  

// Slice  
console.log(b.slice(1, 3))  
console.log(b)  
  
// Length
console.log(b.length)  

let e = [1, 9, 8, 6, 2, 7, 3, 5, 4]  

// in-place sort  
console.log(e.sort())  
console.log(e)  
  
// in-place reverse  
console.log(e.reverse())  
console.log(e)
```

#### 3.2.6 Function
```JavaScript
function hello() {
	console.log('Hello !')
}

function add_nums(a, b){
	return a + b
}
```

#### 3.2.7 Object
```JavaScript
let car = {  
    color: 'blue',  
    type: 'camaro',  
    speed: 0,  
    acc: function() {  
        this.speed += 10  
        console.log(this.speed)  
    },  
    dec: function() {  
        this.speed -= 10  
        console.log(this.speed)  
    }  
}  
car.acc()  
car.dec()
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIwNjcyMjE2MDcsLTUzNTkzMDc2MSwtMj
A5OTIxMjM3Miw5NjA3OTQzMTYsMjg5MzUxNjI2LC04OTk0MDMz
OTksNzkzNjUyNjIwLDE0NjMwMzM0NzMsLTQzODEzODY0NywtOD
E5MTUxNTY3LDE3OTMxNjcxMzcsMTE2MzYyMTQ5OSw3NzU1NTUz
NTQsLTY1MTYyODIyOCwxNzE4NjQ0NDE1LC0xOTc4MDkyMDc5LC
05MjAwMDI4OTAsMTM5MjkxMzY1NywtMTgyMjgxNzM4NV19
-->