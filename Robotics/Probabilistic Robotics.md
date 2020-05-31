<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# Probabilistic Robotics
## 1. Recursive State Estimation
#### 1.1 Math Basics

- Positive Definite & Positive Semi-definite
*Positive Definite*: For an n x n matrix $A$, by given any non-zero vector $x$, $x^TAx>0$ stands, then $A$ is positive definite.
*Positive Semi-definite*: For an n x n matrix $A$, by given any vector $x$, $x^TAx \ge0$ stands, then $A$ is positive definite.

- Gaussian Distribution
*Normal Distribution:  $p(x) = \frac {1}{\sqrt{2\pi\sigma}}exp(-\frac{(x-\mu)^2}{2\sigma^2})$
*Multivariate Gaussian Distribution: $p(x) = \frac{1}{\sqrt{det(2\pi\Sigma)}}exp(-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu))$

#### 1.2 Bayes Filter
Bayes_Filter(bel($x_{t-1}$), $u_t$, $z_t$):
$\qquad$ for all $x_t$:
$\qquad\qquad$$\bar{bel}(x_t)=\sum_{v}{p(x_t|u_t,x_{t-1})bel(x_{t-1})}$


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTIyNDU4NzkwMiw1ODkwMTUxMjQsLTExNj
E0MTgxOSwtNTA1NTgwMDY4LDE0MjkwNDkzNzAsLTIxMzI3Njkz
XX0=
-->