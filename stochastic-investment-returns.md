
# Stochastic investment returns

Provides information about the distribution of financial outcomes which can be
used to find bst estimates and probabilities.

## Fixed rate model

Remember: expected accumulated value $\neq$ accumulated value at expected
rate of return, if $n>1$.
$$
\sum_{j=1}^kp_j(i+i_j)^n \neq \left( 1 + \sum_{j=1}^kp_ji_j\right) ^n
$$

Mean and variance must be calculated from first principles.
It is assumed that the rate of return is unknown until immediately after the
investment is made.

## Varying rate model

\begin{align}
S_n=(1+i_1)(1+i_2)(1+i_3)\dots &(1+i_n) \\
A_n=(1+i_1)(1+i_2)(1+i_3)\dots &(1+i_n) + \\
           (1+i_2)(1+i_3)\dots &(1+i_n) + \\
                               &(1+i_n)
\end{align}

Assume $i$ has mean $j$ and variance $s^2$.

### Moments of $S_n$

\begin{align}
E[S_n]&=\prod_{t=1}^nE[1+i_t] = \prod_{t=1}^n(1+E[i_t])=(1+j)^n \\
E[S_n^2]&=\prod_{t=1}^nE(1+2i_t+i_t^2)=\prod_{t=1}^n(1+2E[i_t]+E[i_t^2]) \\
        &=(1+2j+j^2+s^2)^n\text{ since }E[i_t^2]=(E[i_t])^2+Var(i_t) \\
Var(S_n)&=(1+2j+j^2+s^2) - (1+j)^{2n}
\end{align}

### Moments of $A_n$

$\mu_n = E[A_n]$ and $m_n=E[A_n^2]$

\begin{align}
\mu^n&=(1+j)(1+\mu_{n-1})\text{ so }\mu_n =
    \ddot{s}_n\text{ at }j\text{ where}\\
\ddot{s}_n&=\frac{(1+j)^n-1}{d} \text{ and }d=\frac{j}{1+j} \\
A_n^2&=(1+2i_n+i_n^2)(1+2A_{n-1}+A_{n-1}^2) \\
m_n&=(1+2j+j^2+s^2)(1+2\mu_{n-1}+m_{n-1})\\
Var(A_n)&=E[A_n^2]-(E[A_n])^2=m_n-\mu_n^2
\end{align}

## Lognormal distribution

This is useul because compounding makes investment returns  multiplicative.

Handily, if $X_1\sim ln\mathcal{N}(\mu_2, \sigma_2^2)$ and
$X_2\sim ln\mathcal{N}(\mu_2, \sigma_2^2)$ then
$X_1X_2\sim ln\mathcal{N}(\mu_1+\mu_2, \sigma_1^2+\sigma_2^2)$.

From page 14 in the tables

\begin{align}
E[1+i]&=e^{\mu+\frac{1}{2}\sigma^2} \\
Var(1+i)&=e^{2\mu+\sigma^2}(e^{\sigma^2}-1)
\end{align}

Probabilities accumulations or present values are below a given value.
\begin{align}
S_n&\sim ln\mathcal{N}(n\mu,n\sigma^2)\text{ and }
P(S_n\le s)=\Phi\left(\frac{ln(s)-n\mu}{\sigma\sqrt{n}}\right) \\
V_n&\sim ln\mathcal{N}(-n\mu,n\sigma^2)\text{ and }
P(V_n\le s)=\Phi\left(\frac{ln(s)-(-n\mu)}{\sigma\sqrt{n}}\right)
\end{align}

