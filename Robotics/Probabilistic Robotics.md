<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# Probabilistic Robotics
## 1. Recursive State Estimation
#### 1.1 Math Basics

- Positive Definite & Positive Semi-definite
*Positive Definite*: For an n x n matrix $A$, by given any non-zero vector $x$, $x^TAx>0$ stands, then $A$ is positive definite.
*Positive Semi-definite*: For an n x n matrix $A$, by given any vector $x$, $x^TAx \ge0$ stands, then $A$ is positive definite.

- Gaussian Distribution
*Normal Distribution*: 
$$p(x) = \frac {1}{\sqrt{2\pi\sigma}}exp(-\frac{(x-\mu)^2}{2\sigma^2})$$
*Multivariate Gaussian Distribution*: 
$$p(x) = \frac{1}{\sqrt{det(2\pi\Sigma)}}exp(-\frac{1}{2}(x-\mu)^T\Sigma^{-1}(x-\mu))$$

#### 1.2 Bayes Filter
Bayes_Filter(bel($x_{t-1}$), $u_t$, $z_t$):
$\qquad$ for all m in $x_t$:
$\qquad\qquad$$\bar{bel}(x_t=m)=\sum_{n}{p(x_t|u_t,x_{t-1}=n)bel(x_{t-1}=n)}$
$\qquad\qquad$$bel(x_t=m)=\eta p(z_t|x_t=m)\bar{bel}(x_t=m)$
$\qquad$ return $bel(x_t)$

## 2. Gaussian Filters

#### 2.1 Kalman Filter

**State Transformation Function**
 $$x_t = A_tx_{t-1}+B_tu_t+\varepsilon_t$$
 where $x_t$ and $x_{t-1}$ are state vectors, $u_t$ is the control vector at time t, and $\varepsilon_t$ is the random noise at time t, and we assume it subject to distribution $N(0, R_t)$.

**Measurement Function**
 $$z_t=C_tx_t+\delta_t$$
where $\delta_t$ is the random noise introduced from measurement, which subject to normal distribution $N(0, Q_t)$

**Initial Belief**
$$bel(x_0) \sim N(\mu_0, \Sigma_0)$$

**Kalman Filter Algorithm**

$AlgorithmKalmanFilter(\mu_{t-1}, \Sigma_{t-1},u_t, z_t):$
$\qquad    \bar{\mu_t}= A_t\mu_{t-1}+B_tu_t$
$\qquad    \bar{\Sigma_t} = A_t\Sigma_{t-1}A_t^T+R_t$
$\qquad    K_t = \bar{\Sigma_t}C_t^T(C_t\bar\Sigma_tC_t^T+Q_t)^{-1}$
$\qquad    \mu_t = \bar\mu_t + K_t(z_t-C_t\bar\mu_t)$ 
$\qquad    \Sigma_t = (I-K_tC_t)\bar\Sigma_t$
$\qquad    return\:\;\mu_t, \Sigma_t$

#### 2.2 Extended Kalman Filter

**State Transformation Function**
 $$x_t = g(u_t, x_{t-1})+\varepsilon_t$$
 Where $x_t$ and $x_{t-1}$ are state vectors, $u_t$ is the control vector at time t, and $\varepsilon_t$ is the random noise at time t, and we assume it subject to distribution $N(0, R_t)$. We also denote that $G_t = g'(u_t, \mu_{t-1})$

**Measurement Function**
 $$z_t=h(x_t)+\delta_t$$
Where $\delta_t$ is the random noise introduced from measurement, which subject to normal distribution $N(0, Q_t)$. We also denote that $H_t=h'(\bar\mu_t)$

**Extended Kalman Filter Algorithm**

$ExtendedKalmanFilter(\mu_{t-1}, \Sigma_{t-1},u_t, z_t):$
$\qquad    \bar\mu_t = g(u_t, \mu_{t-1})$
$\qquad    \bar\Sigma_t = G_t\Sigma_{t-1}G_t^T+R_t$
$\qquad    K_t=\bar\Sigma_tH_t^T(H_t\bar\Sigma_tH_t^T+Q_t)^{-1}$
$\qquad    \mu_t = \bar\mu_t + K_t(z_t-h(\bar\mu_t))$
$\qquad    \Sigma_t$
$\qquad    $


<!--stackedit_data:
eyJoaXN0b3J5IjpbLTg4MzYwNjM5Myw3NzgwNzcwMzEsMTI5Mj
c4MzUyNywtMjI5NTY2NTUzLC01NTQ0MjA0NzAsLTU1NDQyMDQ3
MCwtNDM1MTcyNzE3LDEzMTc4OTg3MSwtOTU0NzEwMzE0LC00MT
M3MTk4MDIsNTg5MDE1MTI0LC0xMTYxNDE4MTksLTUwNTU4MDA2
OCwxNDI5MDQ5MzcwLC0yMTMyNzY5M119
-->