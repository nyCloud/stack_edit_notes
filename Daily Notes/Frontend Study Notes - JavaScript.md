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
JavaScript Types
- Undefined & Null
```JavaScript
cash = null
future = undefined
```
- Number
```JavaScript
val_a = 123
val_b = 2.718
val_c = 3e8
```

- Bool
```JavaScript
cond_a = true
cond_b = false
```

- String
```JavaScript
str_a = 'Too Young'
str_b = "Too Simple"
console.log(str_a[0]) // You will get 'T'
console.log(a.concat(b))  // not in-place

// get length
str_a.length
```

REs are also supported in JavaScript
-- format '/body/modifier(optional)'
-- asd

- Array
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

- Function
```JavaScript
function hello() {
	console.log('Hello !')
}

function add_nums(a, b){
	return a + b
}
```

- Object
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
eyJoaXN0b3J5IjpbLTI4MDQ2NDAyOCwtODk5NDAzMzk5LDc5Mz
Y1MjYyMCwxNDYzMDMzNDczLC00MzgxMzg2NDcsLTgxOTE1MTU2
NywxNzkzMTY3MTM3LDExNjM2MjE0OTksNzc1NTU1MzU0LC02NT
E2MjgyMjgsMTcxODY0NDQxNSwtMTk3ODA5MjA3OSwtOTIwMDAy
ODkwLDEzOTI5MTM2NTcsLTE4MjI4MTczODVdfQ==
-->