<script type="text/javascript" src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS_HTML"></script>

# Statistics & Probability
## 1.Basic Probability

### Conditional Probability
$$ P(A|B) = \frac{P(AB)}{P(B)}$$

- If P(A) = P(A|B), then P(AB) = P(A)P(B), because P(A|B) = P(AB) / P(B). When P(AB) = P(A)P(B), we can say that event A and B are independent

### Law of Total Probability
Given a event A and a group of events B_i, if their probabilities are subject to:
$$	\sum_i P(B_i) = 1 \\ \forall B_iB_j=\empty \;\;s.t.\;\; i \ne j $$ 
Then we have 
$$ P(A) = \sum_i P(AB_i) = \sum_iP(B_i)P(A|B_i)$$

### Bayes Equation
$$ P(A|B) = \frac {P(A)P(B|A)} {P(B)} = \frac {P(A)P(B|A)} {\sum_i P(A_i)P(B|A_i)}$$

## 2. Random Variable & Distribution
### 2.1 Discrete Random Distributions
|Distribution| $P(n)$ | $E(f(x))$| Mean | Var | 
-|-|-|-|-
| Binomial | $$\begin{pmatrix} n \\ k \end{pmatrix}p^k(1-p)^{n-k}$$ | $$np$$ | $$np$$ | $$np(1-p)$$ 
| Poisson | $$\frac {\lambda^ke^{-\lambda}}{k!}$$ | $$\lambda$$ | $$\lambda$$ | $$\lambda$$


- Binomial Distribution: Making n consecutive experiments and for each experiment $p(x=1)=p$. The total times the event $x=1$ happen follows Binomial distribution.

- Poisson: In the interval $[0, 1]$, given that in any interval $[t, t+\Delta t]$, the probablity a single event happen is $(\lambda\Delta t)$, then the total times the events happen follows Poisson distribution.

### 2.2 Continuous Random Distributions
CDF (Cumulative Distribution Function): $F(x) = p(X<x)$

PMF (Probability Mass Function): $f(x) = f'(x)$
- $f(x)\ge0$
- $\int_{-\infty}^{\infty}f(x)dx=1$
- $P(a \le X \le b) = F(b) - F(a) = \int_a^bf(x)dx$

|Distribution| PMF | $E(f(x))$| Mean | Var | 
-|-|-|-|-
| Gaussian | $$f(x) = \frac{1}{\sigma\sqrt{2\pi}}exp(-\frac{(x-\mu)^2}{})$$
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTI3NjMyODE2LDE4NTc5NTQ2NDQsMTI2Mj
U2ODYzMCwtMTQ1Mzk5OTc0NCwxMjk4MTAxOTI0LDExNTY3NzU3
MDYsMjA2MjI5MzA2OSwzMjc5NTI4NzUsLTE0MTIzNDYyOTQsLT
E2NjM1NzE5OTQsMjQ3MzgyNjU3LC00NjAxOTkwNDIsMTc3MDU5
MzA1LC0xMzM1MzAwOTg0XX0=
-->