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

#### Basic Example
Here is a simple example to compute gradient to a column vector.

$$ y = x x^T$$
$$ \frac{\partial y}{\partial x} = 2x $$

```python
x = mx.nd.arange(4)
x.attach_grad()
with autograd.record():
	y = nd.dot(x, x)
y.backwardx()
print(x.grad)
# result = [0, 2, 4, 6]
```
Please note that when y is not a scalar, MxNet will sum the elements in y to get a new variable y by default, and then find analytical gradient of the new y wrt x.

#### Detach Function
Detach function will create a new constant and detach its former computation steps.
```python
x = nd.arange(4)
x.attach_grad()
with autograd.record():
    y = x * x
    z = y * x
z.backward()
print(x.grad)
# 3x^2 = [ 0.  3. 12. 27.]

x = nd.arange(4)
x.attach_grad()
with autograd.record():
    y = x * x
    u = y.detach()
    z = u * x
z.backward()
print(x.grad)
# dz/dx = u = x^2 = [0. 1. 4. 9.]
```


#### Internal Variables

#### Head Gradients

#### Python Control Flow

#### Training Mode and Prediction Mode


<!--stackedit_data:
eyJoaXN0b3J5IjpbOTMzMzA3NDg3LC0yNjA1MjU5NzIsMzUzND
Y1MTIxLC0xMTIwNDEzNjMzLDE1MzM1Mjg0NjYsMTI1MDYzMjU5
OCwxNDE3ODQxNTUxLC0xNDIzMTk3MjgxLDEyMDE3MDk0OTAsLT
EwMjQzOTM0NzBdfQ==
-->