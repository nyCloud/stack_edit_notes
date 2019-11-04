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
### Discrete Random Distributions
|Distribution| $P(n)$ | $E(f(x))$| Mean | Var | 
-|-|-|-|-
| Binomial | $$\begin{pmatrix} n \\ k \end{pmatrix}p^k(1-p)^{n-k}$$ | $$np$$ | $$np$$ | $$np(1-p)$$ 
| Poisson | $$\frac {\lambda^ke^{-\lambda}}{k!}$$ | $$\lambda$$ | $$\lambda$$ | $$\lambda$$


- Binomial Distribution: Making n consecutive experiments and for each experiment $p(x=1)=p$. The total times the event $x=1$ happen follows Binomial distribution.

- Poisson: In the interval $[0, 1]$, given that in any interval $[t, t+\Delta t]$, the probablity a single event happen is $(\lambda\Delta t)$, then the total times the events happen follows Poisson distribution.

### Continuous Random Distributions
CDF (Cumulative Distribution Function): $F(x) = p(X<x)$
PMF (Probability Mass Function): $f(x) = f'(x)$
- $f(x)\ge0$
- $\int_{-\infty}^{\infty}f(x)dx=1$
- $P(a \le X \le b) = F(b) - F(a) = \int_a^bf(x)dx$

<!--stackedit_data:
eyJoaXN0b3J5IjpbODAzMTcxMTY5LDEyNjI1Njg2MzAsLTE0NT
M5OTk3NDQsMTI5ODEwMTkyNCwxMTU2Nzc1NzA2LDIwNjIyOTMw
NjksMzI3OTUyODc1LC0xNDEyMzQ2Mjk0LC0xNjYzNTcxOTk0LD
I0NzM4MjY1NywtNDYwMTk5MDQyLDE3NzA1OTMwNSwtMTMzNTMw
MDk4NF19
-->