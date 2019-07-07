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

### 1.2. Automatic Differentiation

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

Besides, when calling function u.attach_grad(), u = u.detach() will be implicitly called. 
```python
y = nd.ones(4) * 2 
y.attach_grad() 
with autograd.record():
	u = x * y 
	u.attach_grad() 
	z = u + x 
z.backward()
print(x.grad, u.grad, y.grad)
``` 

when executing inside autograd.record() mode, autograd.is_training() will return True, else False.

### 1.3 Linear Neural Networks

#### 1.3.1 Linear Regression

Let's get start with Data Loaders, An example of simple data iterator:
```python
def data_iter(batch_size, features, labels):
	
	num_examples = len(features)
	indices = list(range(num_examples))  
	random.shuffle(indices) 
	
	for i in range(0, num_examples, batch_size):
		j = nd.array(indices[i: min(i + batch_size, num_examples)]) 
		yield features.take(j), labels.take(j) 
		# The “take” function will then return the corresponding element 
		# based on the indices
```

Or we can also use the DataLoader provided by MxNet
```python
def load_array(data_arrays, batch_size, is_train=True):

	"""Construct a Gluon data loader""" 
	dataset = gluon.data.ArrayDataset(*data_arrays) 
	return gluon.data.DataLoader(dataset, batch_size, shuffle=is_train) 

batch_size = 10 
data_iter = load_array((features, labels), batch_size)
```

Linear Regression in MxNet style
 
```python
from mxnet import init
from mxnet.gluon import nn
from mxnet.gluon import loss

# Create sequential network
net =nn.Sequential()

# Add single dense layer with single output
# In MxNet, input size will be automatically infered
net.add(nn.Dense(1))

# Initialize layer
net.initialize(init.Normal(bias=0, sigma=0.01))

# Define loss function
l = loss.L2Loss()

# Indicate Optimizer
t_coef = {'learning_rate': 0.03}
trainer = gluon.Trainer(net.collect_params(), 'sgd', t_coef)

# Train the Model
num_epochs = 3 
for epoch in range(1, num_epochs + 1): 
	
	for X, y in data_iter: 
		with autograd.record(): 
			l = loss(net(X), y) 
		l.backward() 
		trainer.step(batch_size) 
	
	l = loss(net(features), labels) 
	print('epoch %d, loss: %f' % (epoch, l.mean().asnumpy()))
```

#### 1.3.2 Linear Classification

__Model__
To define the model of linear classification, we will need Softmax Function:
$$ \hat{y} = softmax(o) $$
where
$$p(y|x)=\hat{y}_i = \frac{exp(o_i)}{\sum_j exp(o_j)}$$
most likely class
$$\hat{c}(o)=\underset{i}{\operatorname{argmax}} (\hat{y}_i)$$

And the prediction model is defined as
$$ \hat{y}_i = softmax(Wx_i + b)$$

__Loss__
We define the loss function as:
$$ l = -log\;p(y|x) = -\sum_jy_jlog(\hat{y}_j)$$
Note that yj is in one hot representation, thus this term works as a selector.
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMTI5MjI1NTQsLTQ5NzI2NzY2MiwtMT
kyMjQ0NzkzMiwxMzg5MzEzNjM4LDExMjYyNzM5OTYsLTg0MzA3
NTc0NywzNjIwNDc3MDEsLTQ2NjAwNTIzMywtMTA4NDI1NjkwNy
wtNzIwMDk5OTgsMTkxNDE3NTY3NCwtMjYwNTI1OTcyLDM1MzQ2
NTEyMSwtMTEyMDQxMzYzMywxNTMzNTI4NDY2LDEyNTA2MzI1OT
gsMTQxNzg0MTU1MSwtMTQyMzE5NzI4MSwxMjAxNzA5NDkwLC0x
MDI0MzkzNDcwXX0=
-->