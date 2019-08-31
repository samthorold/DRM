
# Measures of investment risk

## Variance

Mathematically tractable and leads to tidy solutions for optimal portfolios
within the context of mean-variance portfolio theory.

Continuous random varianble: $Var=\int_{-\infty}^\infty (\mu-x)^2f(x)dx$

Discrete random varianble: $Var=\sum_x (\mu-x)^2P(X=x)$

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

## Example - value of fund

_An investor wishes to save for a retirement fund of £100,000 in 10 years time.
The investor can purchase non-dividend-paying shares governed by the SDE
$dS_t=S_t(\mu dt+\sigma dZ_t)$.

- $Z_t$ is a standard Brownian motion
- $\mu=12%$
- $\sigma=25%
- $t$ is in years
- $S_0=1$

Derive the distribution of $S_t$
\[
S_t\sim lnN(0.08875t, 0.25^2t)
\]

Calculate the amount $A$ the investor would need to invest to have a 50:50
probability of building up a retirement fund of £100,000 in 10 years.

\[
A=100,000e^{-0.8875}=£41,168
\]

Calulate the following risk measures applied to the difference between the
value of the fund and £100,000 if the investor invests in $A$.

If the initial amount is invested in $A$, then the fund after 10 years is
\begin{align}
F_{10} &= Ae^{0.8875+0.25Z_{10}}\\
       &= 100,000e^{-0.8875}e^{0.8875+0.25Z_{10}}\\
       &= 100,000e^{0.25Z_{10}}
\end{align}

Variance:
\begin{align}
Var(100,000-F_{10}) &= Var(F_{10})\\
                    &= Var(100,000e^{0.25Z_{10}})\\
                    &= 100,000^2e^{0.25Z_{10}}
\end{align}

To find $Var(e^{0.25Z_{10}})$ note that $Z_{10}\sim N(0,1)$.
This means $0.25Z_{10}\sim N(0, 0.25^2\times 10)=N(0, 0.625)$.
Therefore, $e^{0.25z_{10}}\sim lnN(0, 0.625)$.

Using the formula for variance of the lognormal distribution
\[
E[e^{0.25Z_{10}}]=e^{0.625}(e^{0.625}-1)=1.622097
\]
So
\[
Var(100,000-F_{10})=100,000^2\times 1.622097=(£127,362)^2
\]

Shortfall probability relative to £90,000:
\begin{align}
P(F_{10}<90,000)&=P(100,000e^{0.25Z_{10}}<90,000)\\
  &= P(e^{0.25Z_{10}}<0.9)\\
  &= P(0.25Z_{10}<ln0.9)\\
  &= P(Z_{10}<\frac{ln0.9}{0.25})\\
  &= P(N(0,10)<\frac{ln0.9}{0.25})\\
  &= P(N(0,1)<\frac{ln0.9}{0.25\sqrt{10}})\\
  &= \Phi(-0.1333)
\end{align}
Interpolating from the Tables:
\[
\Phi(0.1333)=0.33\times\Phi(0.14)+0.67\times\Phi(0.13)=0.55304
\]
So
\[
P(F_{10}<90,000)=1-\Phi(0.1333)=0.44696
\]

99% VaR:

To find the 99% VaR we need to find the value $t$ such that the fund will
fall below $t$ with a probability of 1% i.e $P(F_{10}<t)=0.01$.

Since $Z_{10}\sim N(0,10)$ and this distribution is equivalent to
$sqrt{10}\times N(0,1)$, the 1% percentile for $Z_{10}$ is
$\sqrt{10}\times-2.3263=-7.3564$.

But, $F_{10}=100,000e^{0.25Z_{10}}. So the 1% percentile for $F_{10}$ is
\[
t=100,000e^{0.25(-7.3564)}=£15,896
\]
So the 99% VaR compared to the target of £100,000 is
$£100,000-15,896=£84,104$.
