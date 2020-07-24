# Probabilistic Robotics
## 1. Recursive State Estimation
### 1.1 Math Basics

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

Bayes Filter is so important that so many probabilistic robotics algorithms are based on it. It provides a paradigm to describe the problem when we have:
- $x_{t-1}$: a prior estimation of states
- $u_t$: a description of initiative values that influence the state 
- $z_t$: a measurement of the new state

We change the world and then we measure the world. 
 


## 2. Gaussian Filters

### 2.1 Kalman Filter (KF)

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

### 2.2 Extended Kalman Filter (EKF)

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
$\qquad    \Sigma_t=(I-K_tH_t)\bar\Sigma_t$
$\qquad    return\;\;\mu_t, \Sigma_t$

## 3 Non-parametric Filters
### 3.1 Discrete Bayes Filter
Similar as forward steps of Hidden Markov Model.

$DiscreteBayesFilter(p_k^{t-1},u_t,z_t):$
$\qquad    for\;all\;k\;in\;p:$
$\qquad \qquad    \bar p_k^t = \sum_i{p(X_t=x_k|u_t,X_t-1=x_i)p_i^{t-1}}$
$\qquad \qquad    p_k^t = \eta p(z_t|X_t=x_k)\bar p_k^t$
$\qquad    return\;p_k^t$

**Histogram Filter**
Apply Discrete Bayes Filter under continuous space, we'll have Histogram Filter.

**Binary Bayes Filter**
Certain problems in robotics are best formulated as estimation problems with binary
state that does not change over time. Problems of this type arise if a robot estimates
a fixed binary quantity in the environment from a sequence of sensor measurements.
Since the state is static, the belief is a function of the measurements:
$$bel_t(x)=p(x|z_{1:t,u_1:t})=p(x|z_{1:t})$$

$BinaryBayesFilter(l_{t-1},z_t):$
$\qquad  l_t=l_{t-1}+log \frac{p(x|z_t)}{1-p(x|z_t)}-log \frac{p(x)}{1-p(x)}$
$\qquad  return\;l_t$

### 3.2 Particle Filter
$ParticleFilter(X_{t-1}, u_t, z_t):$
$\qquad \bar X_t=X_t=\empty$
$\qquad  for\;i\;in\;range(n):$
$\qquad \qquad  x_t^i=sample(p(x_t|u_t,x_{t-1}^i))$
$\qquad \qquad  w_t^i=p(z_t|x_t^i)$
$\qquad \qquad \bar X_t.add((x_t^i, w_t^i))$
$\qquad  for\;i\;in\;range(n):$
$\qquad  \qquad X_t.add(draw\;x_t\;with\;prob\;w_t)$
$\qquad  return\;X_t$

# 3. Localization & Position Estimation

<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyNzA5NDczMCwtODA4ODQ2MDY4LC0xMT
I0Njc3NzQ3LC0zMzI3NDM3NzQsMTQ2Njc4NDQ5NSwtMzExMjY0
ODc1LC0yMDIyMTU3ODIxLC0xMDQ0MTg0NDcsLTU1NDczNzk5My
wtMTcyMTU4MzgwNyw1NTQ0MzM4NjAsMTY1MTA0MDI5Nyw2MzM4
Mjk2NDcsLTE1Nzc5NDY4MDcsLTEzNDYwNDk2NjEsMTE3NDA4ND
U0MSw1NDc3MDMxOTYsLTU4ODMwNDIyNCwtOTg5NTQwMzQ0LDc1
ODQ3NjkwMF19
-->