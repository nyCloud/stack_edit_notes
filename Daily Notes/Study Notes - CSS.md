# Study Notes - CSS
Nan Yu | April 2019   
  
## CSS

### 1. Intro

A CSS rule is usually consisted by a selection and several css statements.
```css
/* selector {stmt1; stmt2}*/
h1 {color: blue; font-size: 12px;}
```

### 2. CSS Selector
#### 2.1 Type Selector
```css
p  {  
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

#### 2.1 Class Selector
Class selectors apply the style on elements with indicated class name.
```css
.center {text-align:center;}
```
Class selector for specific html element.
```css
p.center_text  {text-align:center;}
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1Mjg3OTczODksLTg0NTI2NzY2MywxND
E5NDE5OTg5XX0=
-->