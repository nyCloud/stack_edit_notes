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
-  $E[X_1\cdot X_2 \cdot ... \cdot X_n] = E[X_1]\cdot E[X_2] \cdot ... \cdot[X_n]$ ( $X_i$ are all independent)
- $E[f(X)] = \sum_i f(x_i) \cdot p(x_i)$
- $E[kX] = kE[x]$
<!--stackedit_data:
eyJoaXN0b3J5IjpbNzI1NTQ1NTk3LDE5MzAzNzQ1NDYsMTQ5MD
MyMTgzNiwtNjAzMjYwNzUxLDM3Mjk1MDU5MywtNTUzODk3OTIx
LDEyMzMxMzEzMjQsLTExMDYzMDUyNjAsMTk1NjM3MzUxLDE1MT
AwNjA2MDAsMTY0MDk0ODg3MywxMzM0MjAwOTU3LDE4NTc5NTQ2
NDQsMTI2MjU2ODYzMCwtMTQ1Mzk5OTc0NCwxMjk4MTAxOTI0LD
ExNTY3NzU3MDYsMjA2MjI5MzA2OSwzMjc5NTI4NzUsLTE0MTIz
NDYyOTRdfQ==
-->