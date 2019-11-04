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
|Name| ASCII | HTML | 
----------------- | ---------------------------- | ----------------
| Single backticks | `'Isn't this fun?'` | 'Isn't this fun?' | 

<!--stackedit_data:
eyJoaXN0b3J5IjpbMjA2MjI5MzA2OSwzMjc5NTI4NzUsLTE0MT
IzNDYyOTQsLTE2NjM1NzE5OTQsMjQ3MzgyNjU3LC00NjAxOTkw
NDIsMTc3MDU5MzA1LC0xMzM1MzAwOTg0XX0=
-->