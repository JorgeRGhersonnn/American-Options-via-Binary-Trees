# Pricing American Options via Binary Tree Model Analysis

## Introduction
American options represent a fundamental class of financial derivatives that grant the holder the right, but not the obligation, to exercise the option at any time up to and including the expiration date. For said assets, the traditional Black-Scholes model does not necessarilly apply since this introduces a significant challenge in valuation with the need to use numerical methods for accurate pricing.

For this project, we implement and analyze the binary tree model for pricing American options, demonstrating the impact of early exercise premiums on option pricing.

## Framework
### Binomial Tree Model
The binomial tree model operates under the risk-neutral probability measure 

$$
p = \frac{e^{r \delta t} - d}{u-d},
$$
where $r$ is the risk-free interest rate, $\delta t$ is the time step length, $u$ is the up factor, and $d$ is the down factor. These factors are dependent on the volatility of the underlying asset $\sigma$, such that

$$
u = e^{\sigma\sqrt{\delta t}}
$$

$$
d = \frac{1}{u} = e^{-\sigma\sqrt{\delta t}}
$$

where the time step is defined as the ratio between the time to expiration $T$ and the number of steps $n$. 

### Asset Price Evolution
Consider a stock at an initial price $S_0$. We analyze the evolution of the price at a specific node $(i,j)$ based on the time step $i$ and the number of up moves $j$, such that

$$ 
S(i,j) = S_0 u^j d^{i-j}, \quad 0\leq i \leq n, \text{ and } 0\leq j\leq i
$$
