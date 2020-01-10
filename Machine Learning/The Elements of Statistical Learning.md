<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

#  The Elements of Statistical Learning
## 1. Linear Methods for Regression
### 1.1 Least Squares Linear Regression
$$\hat y= \beta_0 + \sum_{i=1}^{p} X_i\beta_i $$
Rewrite the equation in matrix form, we'll get:
$$\hat y = X\hat\beta$$
Least square solution for regression:
$$\hat \beta=(X^TX)^{-1}X^Ty$$

### 1.2 Shrinkage Methods
#### Ridge Regression
$$\hat \beta^{ridge} = \argmin_\beta \{(y - X\beta)^T(y - X\beta) + \lambda \beta^T\beta\}$$
Solving the equation we will get:


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg2OTE1MjU0MCwtNjY1NzcxMjk3LC0xNj
A4MDEzNjldfQ==
-->