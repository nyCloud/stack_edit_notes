# MxNet Notes
<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

## 1. NDArray
### 1.1 Basic Operations
```python
## Create NDArray

# consecutive integers
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

## Matrix operations

# Element-wise
# + - * / **
# e^x => x.exp()

# Transpose 
x = x.T

# Matmul
mul = mx.nd.dot(x, y)

# Sum & norm * mean
s = x.sum()
n = x.norm().asscalar()
m = x.mean().asscalar()

# Concat
# Vertical
mx.nd.concat(x, x, x, dim = 0)
# Hori
mx.nd.concat(x, x, dim = 1)

# Inplace operation
x[:] = x + y

# npArray <=> NDArray
numpy_array = np.ones((3, 3))
mx_array = mx.nd.array(numpy_array)
numpy_array = mx_array.asnumpy()

```

### 1.2. Automatic Differentiaion

Here is a simple example to compute gradient to a column vector.

```python
x = mx.nd.arange(4)
x.attach_grad()
with autograd.record():
	y = nd.dot(x, x)
y.backwardx()
print(x.grad)
# result = [0, 2, 4, 6]
```


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMjA0MTM2MzMsMTUzMzUyODQ2NiwxMj
UwNjMyNTk4LDE0MTc4NDE1NTEsLTE0MjMxOTcyODEsMTIwMTcw
OTQ5MCwtMTAyNDM5MzQ3MF19
-->