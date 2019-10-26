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
$$R(t) = exp(t\cdot\hat\phi(t))$$
After expanding the equation through Taylor series:
$$R(t)=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
where $$\phi=\theta a \;\;and\;\;|a|=1$$

### From rotation matrix to vector (SO3 to so3)
$$ \theta = arccos(\frac{tr(R)-1}{2}) $$
then solve eigen of function
$$ Rn=n\;\;\;(eigenval=1)$$

### 1.2. SE3 and se3
$$se(3)=\{ \xi=\begin{bmatrix} \rho \\ \phi\end{bmatrix} \in R^6, \hat\xi= \begin{bmatrix} \hat\phi & \rho \\ 0^T & 0\end{bmatrix} \}$$

$$exp(x) = \sum_i^\infty \frac {x^i}{i!}$$
$$sin(x) = $$
$$cos(x)= $$


<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM3MzY1MTMzMywtMjU1MTU4MTUzLDIxMj
MzMjc2MTQsMTc5NjA1NjU3NCwtOTc2MzQ0ODQwLDg1OTY3MjQ3
MSwtMTc2ODgyNTcyNV19
-->