# Study Notes - CSS
Nan Yu | April 2019   
  
## CSS

### 1. Intro

A CSS rule is usually consisted by a selection and several css statements.
```css
/* selector {stmt1; stmt2}*/
h1 {color: blue; font-size: 12px;}
```
**How to use CSS**
- External Style Sheet
```html
<head>
	<link rel="stylesheet" type="text/css" href="mystyle.css">  
</head>
```

- Internal Style Sheet
```css
<head>
<style>
hr { color:sienna; } 

p { margin-left:20px;} 

body{
	background-image:url("images/back40.gif");
}
</style>
</head>
```

- Inner Style
```css

```



### 2. CSS Selector
#### 2.1 Type Selector
```css
p {  
	color:red;  
	text-align:center;  
}
```

#### 2.2 ID Selector 
ID selectors apply the CSS style on elements with indicated ID.
```css
/* This style will apply to element with <id = 'id1'>  */
#id1 {
	text-align: center;
	color: red;
}
```

#### 2.3 Class Selector
Class selectors apply the style on elements with indicated class name.
```css
.center {text-align:center;}
```
Class selector for specific html element.
```css
p.center_text  {text-align:center;}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbNDc0NjgxODI4LC04NDUyNjc2NjMsMTQxOT
QxOTk4OV19
-->