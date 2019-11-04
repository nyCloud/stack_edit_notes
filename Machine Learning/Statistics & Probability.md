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
Discrete Random Distributions
|Distribution| $P(n)$ | $E(f(x))$| Mean | Var | 
-|-|-|-|-
| Binomial | $\begin{pmatrix} n \\ k \end{pmatrix}p^k(1-p)^{n-k}$ | $np$ | $np$ | $np(1-p)$ 
| 

- Binomial Distribution: Making n consecutive experiments and for each experiment $p(x=1)=p$
- Poisson: In the interval $[0, 1]$, given that in any interval $[t, t+\Delta t]$, the probablity a single event happen is $(\lambda\Delta t)$, then the total 
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwMjQ3NzQ4NzgsLTE0NTM5OTk3NDQsMT
I5ODEwMTkyNCwxMTU2Nzc1NzA2LDIwNjIyOTMwNjksMzI3OTUy
ODc1LC0xNDEyMzQ2Mjk0LC0xNjYzNTcxOTk0LDI0NzM4MjY1Ny
wtNDYwMTk5MDQyLDE3NzA1OTMwNSwtMTMzNTMwMDk4NF19
-->