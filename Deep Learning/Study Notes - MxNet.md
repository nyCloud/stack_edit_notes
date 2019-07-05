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

#
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTM0NjEyOTU2MSwtMTAyNDM5MzQ3MF19
-->