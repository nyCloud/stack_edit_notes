# Frontend Study Notes  
Nan Yu | April 2019   
  
## HTML  
### 1. Brief Introduction
```html
<!DOCTYPE  html>  
<html>  
	<head> 
		<meta  charset="utf-8">  
		<title>HTML Introduction</title>  
	</head>
	  
	<body>  
		<h1>A title</h1>  
		<p>A paragraph</p>  
	</body>  

</html>
```
html: basic root element
head: meta data
body: visible content


### 1.1 Elements in Head
```html
<head>
	<!-- link css file -->
	<link  rel="stylesheet"  type="text/css"  href="mystyle.css">
	
	<!-- inner css format -->
	<style  type="text/css"> 
		body {background-color:yellow} 
		p {color:blue}  
	</style>
	
	<!-- javascripts -->
	<script> ... </script>
</head>
```

### 2.  HTML Elements

#### 2.1 Heading
```html
<h1> Heading is labeled from h1 to h6 </h1>
```

#### 2.2 Paragraph
```html
<p> This is a paragraph </p>

<!-- bold & italic -->
<p> <b>bold</b> <i>italic</i> </p>

<!-- css -->
<p style='color:blue;'> blue text </p>
```

#### 2.3 Link
```html
<a href='http://www.google.com'> this is a link </a>

<!-- open in a new window -->
<a href='http://www.google.com' target='_blank'> this is a link </a>
```
#### 2.4 Image
```html
<img src='/images/log.png' width='100' height='100' />

<!-- alternative source or fail prompt -->
<img src='/logo.png' alt='/fail.png'>


```

#### 2.5 Table
```html
<table  border="1">  
	<tr>  
		<th>Header 1</th>  
		<th>Header 2</th>  
	</tr>
	
	<tr>  
		<td>row 1, cell 1</td>  
		<td>row 1, cell 2</td>  
	</tr>  
	
	<tr>  
		<td>row 2, cell 1</td>  
		<td>row 2, cell 2</td>  
	</tr>  
</table>
```

#### 2.6 List
```html
<!-- unordered -->
<ul>
	<li>Apple</li>
	<li>Banana</li>
</ul>

<!-- ordered -->
<ol>
	<li>Apple</li>
	<li>Banana</li>
</ol>

<!-- self defined -->
<dl>
	<dt>Apple</dt>
		<dd>-Sweet</dd>
		<dd>-Sour</dd>
<dl>
```

#### 2.7 Div
```html
<div id="menu1" style="background-color:#FFD700;height:100px;width:10%;float:left;margin:auto;">
B1
</div>

<div id="menu2" style="background-color:#FFD700;height:100px;width:10%;float:right;margin:auto;">
B2
</div>
	
<div id="content" style="background-color:#EEEEEE;height:100px;width:80%;float:left;margin:auto;">
C</div>

<div id="footer" style="background-color:#0099CC;clear:both;text-align:center;">
D</div>

```

#### 2.8 Form
```html
<form method="get">
  <input list="browsers" name="browser">
  <datalist id="browsers">
    <option value="Internet Explorer">
    <option value="Firefox">
    <option value="Chrome">
    <option value="Opera">
    <option value="Safari">
  </datalist>
  <input type="submit">
</form>
```

#### 2.X Others
```html
<br> <!-- change line -->
<hr> <!-- split line -->
```
### 3. HTML Attributes
* class: class name for html element
* id: unique id for html element
* style: assign inline style

## CSS  
  
## Java Script  
  
## Vue  
  
## Flask

## MongoDB

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzAyMTMyMDY0LDMxNDU0NDgwOCwtNDMxNj
I3MDIyLDI1MTMwOTE1NiwtMTYwODgxMTc4MCw4MDQ4MzM3ODAs
MTczMDM4MDA2NiwxOTY2NzcxMTYyLC01MDcyOTIzNTksMTEwNj
c5OTE5LDcwNzc1NTQ4MiwxMzMzNjA1MjAwLDM0NTQ1OTQ3OSwx
OTQ3MTY1NDI4XX0=
-->