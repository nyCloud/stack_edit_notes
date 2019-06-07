# Study Notes - HTML  
Nan Yu | April 2019   
  
## JavaScript
### 1. Intro

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
#### 1.1. Some Tricks for Print
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

### 2. Variables & Types
#### 2.1 Variables
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

#### 2.2 Types
#### 2.2.1 Undefined & Null
```JavaScript
cash = null
future = undefined

console.log(null == undefined) // -> true
console.log(null === undefined) // -> false
```

#### 2.2.2 Number
```JavaScript
val_a = 123
val_b = 2.718
val_c = 3e8
```

#### 2.2.3 Bool
```JavaScript
cond_a = true
cond_b = false
```

#### 2.2.4 String
```JavaScript
str_a = 'Too Young'
str_b = "Too Simple"
console.log(str_a[0]) // You will get 'T'
console.log(a.concat(b))  // not in-place

str_c = '  naive     '
console.log(str_c.trim())
// -> naive

// get length
str_a.length
```

#### 2.2.5 RE
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
			n+: at least one occurrence
			n*: at least zero occurrence
			n?: zero or one occurrence

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
re_date = /[0-9]{1,2}[/][0-9]{1,2}[/][0-9]{4}/
console.log('a aa aaa'.split(re_whitespace))
// -> ['a', 'aa', 'aaa']
console.log('4/24/2019 - 4/27/2019'.search(re_date))
// -> 0
```

####  2.2.6 Array
```JavaScript
let a = [1, 2]  
let b = ['a', 'b', 'c', 'd', 'e']  
let c = [1, 2, 'apple', 4]  

console.log(a)  
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

#### 2.2.7 Object
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

#### 2.2.8 Function
Function is a basic type in JavaScript
```JavaScript
function hello() {
	console.log('Hello !')
}

function add_nums(a, b){
	return a + b
}
```
You can also define functions like following
```JavaScript
add = function(a, b){
	return a + b;
}
add(1, 2); // you will get 3
```

### 3. Statements
#### 3.1 If Statement
```JavaScript
// If statement
if (cond1) {
	console.log('1');
} else if (cond2) {
	console.log('2');
} else {
	console.log('3');
}
```

#### 3.2 For Loop
```JavaScript
// For statement
// C style
for (let i=0; i<2; i++) {
	console.log(i);
}

// Python style
list = ['a','b','c'];
for (let i in list) {
	console.log(i + '_' + list[i]);
}

dict = {'a':0, 'b':1, 'c':2}
for (let k in dict) {
	console.log(k + '_' + dict[k])
}
```

#### 3.3 While Loop
```JavaScript
// While loop
let i = 10;
while (i > 0) {
	console.log(--i);
}

// Do-while Loop
let i = 10;
do {
	console.log(--i);
} while (i > 10);
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTYyNzg1MDgxOV19
-->