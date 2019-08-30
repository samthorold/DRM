
# Measures of investment risk

## Variance

Mathematically tractable and leads to tidy solutions for optimal portfolios
within the context of mean-variance portfolio theory.

Continuous random varianble: $Var=\int_{-\infty}^\infty (\mu-x)^2f(x)dx$

Discrete random varianble: $Var=\sum_x (\mu-x)^2P(X=x)dx$

But, investors care more about downside risk than they do about uncertainty in
general.

## Semi-variance

Continuous random varianble: $Var=\int_{-\infty}^\mu (\mu-x)^2f(x)dx$

Discrete random varianble: $Var=\sum_{x<\mu} (\mu-x)^2P(X=x)$

## Shortfall probability

Continuous random varianble: $Var=\int_{-\infty}^Lf(x)dx$

Discrete random varianble: $Var=\sum_{x<L}P(X=x)$

The benchmark level can be expressed as return on a benchmark fund or an
absolute level.

## Value-at-Risk (VaR)

VaR represents the maximum potential loss on a portfolio over a given period
of time with a given degree of confidence ($1-p$).
It is often calculated assuming investment returns follow a normal distribution,
which may not be appropriate.

Continuous random varianble: $VaR(X)=-t$ where $P(X=x)=p$.

Discrete random varianble: $VaR(X)=-t$ where $t=max(x:P(X<x)\le p)$

## Expected shortfall

Continuous random varianble: $Var=\int_{-\infty}^L(L-x)f(x)dx$

Discrete random varianble: $Var=\sum_{x<L}(L-x)P(X=x)$

Expected shortfall measures are useful for monitoring a fund's exposure to risk
because underperformance to a bench mark is easy to understand.

When $L$ is the VaR with a particular confidence level,
the expected shortfall is known at _TailVaR_.
TailVaR measures the expected loss in excess of the VaR.

It is also possible to calculate the expected shortfall and tailVaR conditional
on a shortfall occurring by dividing through by the shortfall probability.

## Risk measures and utility

If expected return and variance are used as the basis of investment decisions,
it can be shown that this is equivalent to a quadratic utility function.

If expected return and semi-variance below the expected return are used as the
basis of investment decisions, it can be shown this is equivalent to a utility
function that is quadtratic below the expected return and linear above.

Use of a shortfall risk measure corresponds to a utility function that has a
discontinuity at the minimum required return.

## Using insurance to manage risk

Insurers decide which events to offer protection for based on the frequency and
severity of the event.

- Low risk, low liklihood events are not a problem
- Low risk, high liklihood events must be monitored to prevent problems due to
an accumulation of these events
- high risk, low liklihood events are normally insured
- high risk, high liklihood events should be avoided.

Micro-insurance has increased the number of low risk events being insured.
For example, mobiles on holiday.

The _pooling_ of resources can be used to reduce an insurer's risk.

_Adverse selection_ describes the fact that people who know that they are bad
risks are more inclined to take out insurance than those who know they are
good risks.
Insurers will try to find out as much about a person as possible to prevent
risks being inaccurately measured.

_Moral hazard_ is the change in a policy holder's behaviour once insurance has
been taken out, which means the event is more likely to occur.
