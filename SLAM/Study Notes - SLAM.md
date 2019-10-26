<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# SLAM

## 1. Lie Algebra
### 1.1. SO3 and so3
It is not hard to know that:
$$ \dot R(t)R(t)^T=\hat\phi(t)$$
If assume phi is a constant value near t, we'll have:
$$\dot R(t) = \hat\phi R(t) = \begin{bmatrix}  
0 & -\phi_3 & \phi_2 \\  
\phi_3 & 0 & -\phi_1 \\
-\phi_2 & \phi_1 & 0 
\end{bmatrix}R(t)$$

### From rotation vector to matrix (so3 to SO3)
Solving the above equation we will get:
$$R = exp(\hat\phi)$$
After expanding the equation through Taylor series:
$$R=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
where $$\phi=\theta a \;\;and\;\;|a|=1$$

### From rotation matrix to vector (SO3 to so3)
$$ \theta = arccos(\frac{tr(R)-1}{2}) $$
then solve eigen of function
$$ Rn=n\;\;\;(eigenval=1)$$

### 1.2. SE3 and se3
$$se(3)=\{ \xi=\begin{bmatrix} \rho \\ \phi\end{bmatrix} \in R^6, \hat\xi= \begin{bmatrix} \hat\phi & \rho \\ 0^T & 0\end{bmatrix} \}$$

As a reminder, we have Taylor expansion:
$$exp(x) = \sum_{i=0}^\infty \frac {x^i}{i!}$$
$$sin(x) = \sum_{i=0}^\infty \frac {(-1)^i x^{2i+1}}{(2i+1)!}$$
$$cos(x) = \sum_{i=0}^\infty \frac {(-1)^i x^{2i}}{(2i)!}$$


<!--stackedit_data:
eyJoaXN0b3J5IjpbNzcwNjE5NzE2LDE0OTQ0MTUxNzUsLTI1NT
E1ODE1MywyMTIzMzI3NjE0LDE3OTYwNTY1NzQsLTk3NjM0NDg0
MCw4NTk2NzI0NzEsLTE3Njg4MjU3MjVdfQ==
-->