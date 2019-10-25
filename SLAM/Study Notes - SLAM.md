<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# SLAM

## 1. Lie Algebra
It is not hard to know that:
$$ \dot R(t)R(t)^T=\hat\phi(t)$$
Thus:
$$\dot R(t) = \hat\phi(t)R(t) = \begin{bmatrix}  
0 & -\phi_3 & \phi_2 \\  
\phi_3 & 0 & -\phi_1 \\
-\phi_2 & \phi_1 & 0 
\end{bmatrix}R(t)$$
Solving the equation we will get:
$$R(t) = exp(t\cdot\hat\phi(t))$$
After expanding the equation through Taylor series:
$$R(t)=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA5NjEzNTQwLDg1OTY3MjQ3MSwtMTc2OD
gyNTcyNV19
-->