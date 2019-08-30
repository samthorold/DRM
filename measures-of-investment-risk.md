
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

Discrete random varianble: $Var=\sum_{x<\mu} (\mu-x)^2P(X=x)dx$

## Shortfall probability

Continuous random varianble: $Var=\int_{-\infty}^Lf(x)dx$

Discrete random varianble: $Var=\sum_{x<L}P(X=x)dx$

## Value-at-Risk (VaR)

VaR represents the maximum potential loss on a portfolio over a given period
of time with a given degree of confidence ($1-p$).
It is often calculated assuming investment returns follow a normal distribution,
which may not be appropriate.

Continuous random varianble: $VaR(X)=-t$ where $P(X=x)=p$.

Discrete random varianble: $VaR(X)=-t$ where $t=max(x:P(X<x)\le p)$
