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
<!--stackedit_data:
eyJoaXN0b3J5IjpbODU5NjcyNDcxLC0xNzY4ODI1NzI1XX0=
-->