## 9. Occupancy Grid Mapping
**Formulation of Occupancy Grid**
$$p(m|z_{1:t})\;\;m={m_i}$$
$$l_{t,i}= log\frac{p(m_i|z_{1:t})}{1-p(m_i|z_{1:t})}$$
Posterior occupy probability
$$p(m_i|z_{1:t}) = 1-\frac{1}{1+exp(l_{t,i})}$$

**Occupancy Grid Mapping Algorithm (MLE Moving Average)**

$OccupancyGridMapping(l, z_t):$
$\qquad    for\; all\;cell\;m_i\;in\;m:$
$\qquad \qquad   if\;m_i\;in\;observation\;field:$
$\qquad \qquad \qquad    l_{t,i} = l_{t-1,i}+InverseSensorModel(m_i, z_t)-l_0$
$\qquad \qquad else:$
$\qquad \qquad \qquad l_{t,i}=l_{t-1,i}$
$\qquad return\;l$

Where $l_0=log\frac{p(m_i)}{1-p(m_i)}$ and $InverseSensorModel(m_i,z_t)=log\frac{p(m_i|z_t)}{1-p(m_i|z_t)}$



<!--stackedit_data:
eyJoaXN0b3J5IjpbMTUwMzk5MjIwM119
-->