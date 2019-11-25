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

- Conversion to standard Gaussian:; If $X \sim N(\mu, \sigma^2)$, then $Y=(X-\mu)/\sigma \sim N(0,1)$
 
### 3. Features of Random Variable
#### 3.1 Expectation
$$ E[X] = \sum_i p(x_i)\cdot x_i$$
- $E[X_1+X_2+...+X_n] = E[X_1]+ E[X_2]+...+E[X_n]$
-  $E[X_1\cdot X_2 \cdot ... \cdot X_n] = E[X_1]\cdot E[X_2] \cdot ... \cdot[X_n]$ **(Independent $X_i$ Required)**
- $E[f(X)] = \sum_i f(x_i) \cdot p(x_i)$
- $E[kX] = kE[x]$
#### 3.2 Variance
$$ Var(X) = E[X - E[X]]^2 = E(X^2) - (E[X])^2 $$
- $Stddev(X) = \sqrt{Var(x)}$
- $Var(X+k) = Var(x)$
- $Var(kX) = k^2\cdot Var(x)$
- $Var(X_1+...+X_n) = Var(X_1) + ... + Var(X_n)$**(Independent $X_i$ Required)**

#### 3.3 Covariance

$$ Cov[X, Y] = E[(X-E[X])(Y-E[Y])] $$

- $Cov[aX+b, cY+d] = a\cdot c\cdot Cov[X, Y]$ 
- $Cov[X, Y] = E[XY] - E[X]E[Y]$
- If X and Y are independent, $Cov[X, Y] = 0$
- $(Cov[X, Y])^2 \le \sigma_1^2 \sigma_2^2$,  when equal condition stands, $Y = aX +b$ and $a = \sigma_2 / \sigma_1$

#### 3.4 Correlation
$$ Corr[X, Y] = \frac {Cov[X, Y]} {\sigma_1 \sigma_2} $$
(One way to understand correlation is that it is a normalized version of correlation)

- If X and Y are independent, then $Corr[X, Y] = 0$
- $-1 \le Corr[X, Y] \le 1$, only when X and Y have strict linear relationship, equal condition stands.
- When $Corr[X, Y] = 0$, we say there is no correlation between X and Y but it doesn't means X and Y are independent.
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEyMDIxOTQ4Nyw3Njk0OTAxMDgsLTEyOT
M0OTA0NjcsMTE2NjExOTA5OCwxNDg1NTIyMjkzLDEyMTI2MTQ3
OTgsNjEzMjE0MDU5LC0xNzg1MDUwODIzLDcyNTU0NTU5NywxOT
MwMzc0NTQ2LDE0OTAzMjE4MzYsLTYwMzI2MDc1MSwzNzI5NTA1
OTMsLTU1Mzg5NzkyMSwxMjMzMTMxMzI0LC0xMTA2MzA1MjYwLD
E5NTYzNzM1MSwxNTEwMDYwNjAwLDE2NDA5NDg4NzMsMTMzNDIw
MDk1N119
-->