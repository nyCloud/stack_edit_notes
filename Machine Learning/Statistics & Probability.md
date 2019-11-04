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
|Distribution| PMF | Mean | Var | 
-|-|-|-|-
| Binomial | $$\begin{pmatrix} n \\ k \end{pmatrix}p^k(1-p)^{n-k}$$ | $$np$$ | $$np(1-p)$$ 
| Poisson | $$\frac {\lambda^ke^{-\lambda}}{k!}$$ | $$\lambda$$ | $$\lambda$$


- Binomial Distribution: Making n consecutive experiments and for each experiment $p(x=1)=p$. The total times the event $x=1$ happen follows Binomial distribution.

- Poisson: In the interval $[0, 1]$, given that in any interval $[t, t+\Delta t]$, the probablity a single event happen is $(\lambda\Delta t)$, then the total times the events happen follows Poisson distribution.

### 2.2 Continuous Random Distributions
CDF (Cumulative Distribution Function): $F(x) = p(X<x)$

PMF (Probability Mass Function): $f(x) = f'(x)$
- $f(x)\ge0$
- $\int_{-\infty}^{\infty}f(x)dx=1$
- $P(a \le X \le b) = F(b) - F(a) = \int_a^bf(x)dx$

|Distribution| PMF | Mean | Var | 
-|-|-|-|-
| Gaussian | $$f(x) = \frac{1}{\sigma\sqrt{2\pi}}exp(-\frac{(x-\mu)^2}{2\sigma^2})$$ | $$\mu$$ | $$\sigma^2$$
|Std Gaussian | $$f(x) = \frac{1}{\sqrt{2\pi}}exp(-\frac{x^2}{2}) $$ | $$0$$ | $$1$$

- If $x \sim N(\mu, \sigma^2)$
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTYyMzgyMDEyLDEzMzQyMDA5NTcsMTg1Nz
k1NDY0NCwxMjYyNTY4NjMwLC0xNDUzOTk5NzQ0LDEyOTgxMDE5
MjQsMTE1Njc3NTcwNiwyMDYyMjkzMDY5LDMyNzk1Mjg3NSwtMT
QxMjM0NjI5NCwtMTY2MzU3MTk5NCwyNDczODI2NTcsLTQ2MDE5
OTA0MiwxNzcwNTkzMDUsLTEzMzUzMDA5ODRdfQ==
-->