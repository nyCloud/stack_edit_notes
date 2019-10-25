<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# SLAM

## 1. Lie Algebra
It is not hard to know that:
$$ \dot R(t)R(t)^T=\hat\phi(t)$$
If assume phi is a constant value near t, we'll have:
$$\dot R(t) = \hat\phi R(t) = \begin{bmatrix}  
0 & -\phi_3 & \phi_2 \\  
\phi_3 & 0 & -\phi_1 \\
-\phi_2 & \phi_1 & 0 
\end{bmatrix}R(t)$$

### From rotation vector to matrix
Solving the above equation we will get:
$$R(t) = exp(t\cdot\hat\phi(t))$$
After expanding the equation through Taylor series:
$$R(t)=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
where $$\phi=\theta a \;\;and\;\;|a|=1$$

### From rotation matrix to vector
$$ \theta = arccos(\frac{tr(R)-1}{2}) $$
then solve eigen of function
$$ Rn=n$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjExMDI4Mzg3NSwtOTc2MzQ0ODQwLDg1OT
Y3MjQ3MSwtMTc2ODgyNTcyNV19
-->