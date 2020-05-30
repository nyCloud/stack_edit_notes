<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# Probabilistic Robotics
## 1. Recursive State Estimation
#### 1.1 Some Math

- Positive Definite & Positive Semi-definite
*Positive Definite*: For an n x n matrix $A$, by given any non-zero vector $x$, $x^TAx>0$ stands, then $A$ is positive definite.
*Positive Semi-definite*: For an n x n matrix $A$, by given any vector $x$, $x^TAx \ge0$ stands, then $A$ is positive definite.

- Gaussian Distribution
*Normal Distribution:  $p(x) = \frac {1}{\sqrt{2\pi\sigma}}exp(-\frac{(x-\mu)^2}{2\sigma^2})$
*Multivariate Gaussian Distribution: $p(x) = \frac{1}{\sqrt{det(2\pi\Sigma)}}exp(-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu))$

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUwNTU4MDA2OCwxNDI5MDQ5MzcwLC0yMT
MyNzY5M119
-->