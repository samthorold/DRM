
# 5-step method

We want to prove the forumula for the fair price of a derivative
$V_t=e^{-r(n-t)}E_Q[c_n\mid F_t]$.
Working backwards, the steps are;

- Show that a certain portfolio replicates the derivative at all times
- Looking at the definition of a replicating strategy,
we see that we first need a self-financing portfolio
- Looking at the definition of a self-financing portfolio,
we see that we need the holdings in the portfolio to be pre-visible
- To show a process is pre-visible, we have the martingale
representation theorem
- But, the martingale representation theorem requires two martingales
- The discounted share price process is a $Q$-martingale but we need one
more
- The other martingale is constructed from derivative payoff,
discounting this all the way back, past the current time $t$, to time 0.

This is a replicating strategies approach to price derivative.

## Definitions

**Pre-visible**: Known based on information up to but not including time $t$.
Sometimes known as $F_{t^-}$ measurable.
For the binomial model, $t^-=t-1$.

**Complete market**: For any derivative payment $X$, there is a replicating
strategy, $(\phi_t, \psi_t)$.

**Equivalent measure**: Two measures $P$ and $Q$ are equivalent if for any
event, $E$, $P(E)>0$ iff $Q(E)>0$. Bascially, both measures must agree what is
and what is not possible.

**Self-financing strategy**: A strategy is self-financing is there are no cash
inflows or outflows.

**Replicating strategy**: A self-financing strategy for $0\le t<u$ such that
$V_u = \phi_u S_u+\psi_uB_u=X$.
For an initial investment $V_0$ at $t=0$ if we follow the self-financing
strategy we will reproduce the derivative payoff without risk.
We rebalance to have $\phi_t$ units of stock and $\psi_t$ uints of cash
without any inflow or outflow.
The replicating strategy gives the derivative payoff regardless of the value
of $S_u$.

## Cameron-Martin-Girsanov

Helps us with change of measure in ECO423 -- $d\tilde{Z}_t=dW_t+\lambda dt$.


Suppose $Z_t$ is a standard Brownian motion under $P$.
Further, suppose $\gamma_t$ is a pre-visible process.
Then there exists a measure $Q$ equivalent to $P$ and where
\[
\tilde{Z}_t = Z_t + \int_0^t\gamma_sds
\]
is a standard Brownian motion under $Q$.

Conversely, if $Z_t$ is a standard Brownian motion under $P$ and if $Q$ is
equivalent to $P$ then there exists a pre-visible process $\gamma_t$ such that
\[
\tilde{Z}_t = Z_t + \int_0^t\gamma_sds
\]

The CMG theorem tells us that we can change the drift but not the volatility
of Brownian motion.

So if we know $P$ and $\gamma$ then we can get $Q$.
Similarly, if we know $P$ and $Q$ we can get $\gamma_t$.

For geometric Brownian motion, $\gamma=\frac{\mu-r}{\sigma}$.
This is the Sharpe ratio.

## Martingale representation theorem

Suppose $X_t$ and $Y_t$ are martingales under $P$.
The MRT says there exists a pre-visible process $\phi_t$ such that
\[
Y_t=Y_0+\int_0^t\phi_sdX_s\iff dY_t=\phi_tdX_t
\]

We'll see later that $\phi_t$ is the amount of stock to hold in the
replicating portfolio.
To make this a replicating portfolio, it is imperative that the amount of
stock to hold is pre-visible.
The MRT proves that it is. Happy days.

