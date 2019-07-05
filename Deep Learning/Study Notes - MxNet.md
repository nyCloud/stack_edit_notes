# MxNet Notes
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

## 1. NDArray
```python
# Create consecutive integers
x = mx.nd.arange(12)

# Get shape  & size
print(x.shape)
print(x.size)

# Reshape
x.reshape((3,4))
# Support auto infer
x.reshape((3,-1)) 

# Ones, zeros, eye
x = mx.nd.eye(3)
x = mx.nd.zeros((3, 3))
x = mx.nd.ones((3, 3))

# Matrix operations

#
# + - * / **
# e^x => x.exp()
 
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg1NTc4MTMzMSwtMTAyNDM5MzQ3MF19
-->