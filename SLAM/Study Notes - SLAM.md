<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# SLAM

# 1. Lie Algebra

## Appendix I: Some basics in math

Taylor expansion:
$$exp(x) = \sum_{i=0}^\infty \frac {x^i}{i!}$$
$$sin(x) = \sum_{i=0}^\infty \frac {(-1)^i x^{2i+1}}{(2i+1)!}$$
$$cos(x) = \sum_{i=0}^\infty \frac {(-1)^i x^{2i}}{(2i)!}$$

Skew symmetric matrix:
$$a \times b = \hat ab = - \hat b a $$
$$\hat a = \begin{bmatrix}  
0 & -a_3 & a_2 \\  
a_3 & 0 & -a_1 \\
-a_2 & a_1 & 0 \\
\end{bmatrix}$$

$$\hat a\hat a = aa^T - I \;\; and \;\; \hat a\hat a\hat a=-\hat a \;\; given \;\; |a| = 1$$

## 1.1. SO3 and so3
It is not hard to know that:
$$ \dot R(t)R(t)^T=\hat\phi(t)$$
If assume phi is a constant value near t, we'll have:
$$\dot R(t) = \hat\phi R(t) = R(t)$$

### From rotation vector to matrix ($\phi$ to $R$)
Solving the above equation we will get:
$$R = exp(\hat\phi)$$
After expanding the equation through Taylor series:
$$R=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
where $$\phi=\theta a \;\;and\;\;|a|=1$$

### From rotation matrix to vector ($R$ to $\phi$)
$$ \theta = arccos(\frac{tr(R)-1}{2}) $$
In order to get rotation vector, there is one better method then using eigen vector:
$$ \frac{R-R^T}{2} = sin\theta\hat a$$

## 1.2. SE3 and se3
$$se(3)=\{ \xi=\begin{bmatrix} \rho \\ \phi\end{bmatrix} \in R^6, \hat\xi= \begin{bmatrix} \hat\phi & \rho \\ 0^T & 0\end{bmatrix} \}$$

### From lie algebra to transformation matrix ($\xi$ to $T$)
$$exp(\hat\xi) = \begin{bmatrix} R &J\rho \\ 0^T & 1 \end{bmatrix}$$
$$ J = \frac {sin \theta}{\theta}I + (1-\frac{sin\theta}{\theta}aa^T+\frac{1-cos\theta}{\theta}\hat a)$$
$$R=cos(\theta I) + (1-cos\theta)aa^T+sin\theta\hat a$$
where $$\phi=\theta a \;\;and\;\;|a|=1$$

### From transformation matrix to lie algebra ($T$ to $\xi$)
$$ \theta = arccos(\frac{tr(R)-1}{2}) $$

In order to get rotation vector, there is one better method then using eigen vector:
$$ \frac{R-R^T}{2} = sin\theta\hat a$$

After this we got:
$$ J = \frac {sin \theta}{\theta}I + (1-\frac{sin\theta}{\theta})aa^T+\frac{1-cos\theta}{\theta}\hat a$$
and 
$$\rho= J^{-1}  t$$

## 1.3. Derivatives of Lie Algebra
Derivative for SO3
$$ \frac{\partial Rp}{\partial \Delta\phi} = -\hat{(Rp)}$$
Derivative for SE3
$$ \frac {\partial Tp} {\partial \Delta \xi} = \begin{bmatrix} I & -\hat{(Rp+t)} \\ 0^T & 0^T \end{bmatrix}_{4\times6}$$



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTgzNjE0MDYxNCwxNDc3NTkxMzI4LC0xMT
I2NTQ3NDg3LC0xNDIyMzAwMjQ1LC0yOTc3MjA5MzUsNTAyMDM4
MzgwLDIyNDM1NzI3MiwyMjI2NTA1ODgsLTEzMzM5NzgwMDUsMz
g5NzAwMzkzLDMzNTk0NzI1MSwxNDk0NDE1MTc1LC0yNTUxNTgx
NTMsMjEyMzMyNzYxNCwxNzk2MDU2NTc0LC05NzYzNDQ4NDAsOD
U5NjcyNDcxLC0xNzY4ODI1NzI1XX0=
-->