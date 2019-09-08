
# The term structure of interest rates

## Definitions

### Zero-coupon bond

Also known as a discount bond. Pays 1 unit of currency at time $T$ and is traded at time $t<T$.
The price of a discount bond is given by
$$
P(t,T) = \frac{1}{(1+R(t,T))^{T-t}}
$$
where the spot rate $R(t,T)$ is the effective rate of interest applicable over the period $t$ to $T$.

Similarly, with $\tau =T-t$
$$
R(t,t+\tau)=\frac{1}{P(t,t+\tau)^{1/\tau}}-1
$$
and as the number of times the spot rate is "paid" goes to infinity
\begin{align}
P(t,T)&=\frac{1}{(1+R(t,T))^\tau} \\
      &=e^{-r(t,T)\tau}
\end{align}
and the continuously compounded bond yield, or instantaneous spot rate, is calculated with
$$
r(t,T)=-\frac{lnP(t,T)}{\tau}
$$

### The yield curve

**Expectations theory**: Long-term rates are determined purely by expectations of future short-term rates.
The expected final value of investing in a sequence of short-term bonds equals the final value of investing in long-term bonds.

**Market segmentation**: Different agents in the market have different objectives.
Pension funds determine long-term rates, market makers determine short-term rates, and businesses determine medium-term rates.
Each segment is governed by supply and demand of debt within that segment.

**Liquidity preference**: Borrowers prefer to borrow long-term and lenders prefer to lend short-term.
This means forward rates are higher than expected future zero rates and yield curves are upward sloping.

### Short and forward rates

The interest rate charged today for a very short period, such as overnight.
\begin{align}
r(t) &= r(t,t+\delta)=-\frac{\partial}{\partial\delta}lnP(t,t+\delta) \\
     &\approx R(t,t+\delta)
\end{align}

Discrete time forward rate
$$
F(0,t,T)=\left( \frac{P(0,t)}{P(0,T)}\right) ^{\frac{1}{T-t}}-1
$$

Continuous time forward rate
\begin{align}
f(0,t,T)&=\frac{r(0,T)T-r(0,t)t}{T-t} \\
        &=\frac{1}{T-t}ln\frac{P(0,t)}{P(0,T)}
\end{align}
and as $t\rightarrow T$, we get the instantaneous forward rate
\begin{align}
f(0,T)&=r(0,T)+T\frac{\partial r(0,T)}{\partial T} \\
      &=-\frac{\partial}{\partial T}lnP(0,T)
\end{align}
\begin{align}
P(t,T)&=e^{-\int_t^Tf(t,u,u)du} \\
      &=e^{-\int_t^Tf(t,u)du}
\end{align}

## Desirable characteristics of term structure models

**Equilibrium** models start with a theory about the economy, such as mean-reverting interest rates.
Based on the model, the implications for pricing assets is worked out.
Examples include the Vasicek and Cox-Ingersoll-Ross models.
Equilibrium models rarely reproduce observed term structures.

**No arbitrage models** use the term structure as an input and are formulated to adhere to the no arbitrage principal.
An example is the Hill-White model.

Both models are arbitrage free, just their starting intuition is different.

We would like models to be

- Arbitrage free.
- Positive interest rate. Depends on application though, some countries have negative nominal rates.
- Mean-reversion.
- Easy to use to calculate prices of bonds and derivatives.
- Realsitic dynamics.
- Fit historical data.
- Easy to calibrate.
- Flexible enough to cope with a variety of derivative contracts.

## Models of term structure

We can use an argument similar to that for the Black-Scholes models using the martingale approach to demonstrate
$$
P(t,T)=E_Q\left[ e^{-\int_t^Tr_udu}\mid F_t\right]
$$
since the payoff of a bond is 1 and any information before time $t$ is irrelevant.

We assume the short rate is driven by the diffusion
$$
dr_t=\mu(t,r_t)dt+\sigma(t,r_t)d\widetilde{W}_t
$$
where $\widetilde{W}_t$ is a Wiener process under the martingale measure.

We define a bank account process as
$$
dB_t=r_tB_tdt
$$
and
$$
B_t=e^{\int_0^tr_udu}
$$

All discounted assets must be Q-martingales and $B_t$ is known at time $t$.
\begin{align}
\frac{P(t,T)}{B_t}&=E_Q\left[\frac{1}{B_T}\mid F_t\right] \\
            P(t,T)&=E_Q\left[\frac{B_t}{B_T}\mid F_t\right] \\
            P(t,T)&=E_Q\left[ e^{-\int_t^Tr_udu}\mid F_t\right]
\end{align}

We assume that the discount bond process is some deterministic function of the short-rate process, $r_t$.
$$
P(t,T)=g(t,r_t)
$$
so
\begin{align}
d\left(\frac{P(t,T)}{B_t}\right) &=d\left(g(t,r_t)B_t^{-1}\right) \\
  &=B_t^{-1}\left[ d\left(g(t,r_t)\right) -r_tg(t,r_t)dt\right]
\end{align}

Applying Ito's lemma to this function gives
\begin{align}
d\left(\frac{P(t,T)}{B_t}\right)&=
B_t^{-1}\left(
\frac{\partial g(t,r_t)}{\partial t}+
\frac{\partial g(t,r_t)}{\partial r_t}\mu(t,r_t)+
\frac{1}{2}\frac{\partial^2 g(t,r_t)}{\partial r_t^2}\sigma^2(t,r_t)-
r_tg(t,r_t)
\right) dt \\
&+B_t^{-1}\frac{\partial g(t,r_t)}{\partial r_t}\sigma(t,r_t)d\widetilde{W}_t
\end{align}
For this to be a Q-martingale, we require
$$
\frac{\partial g(t,r_t)}{\partial t}+
\frac{\partial g(t,r_t)}{\partial r_t}\mu(t,r_t)+
\frac{1}{2}\frac{\partial^2 g(t,r_t)}{\partial r_t^2}\sigma^2(t,r_t)-
r_tg(t,r_t)
=0
$$

### Vasicek model

$$
dr_t = \alpha(\mu-r_t)dt + \sigma d\widetilde{W}_t
$$
Which gives the pde
$$
\frac{\partial g(t,r_t)}{\partial t}+
\frac{\partial g(t,r_t)}{\partial r_t}\alpha(\mu-r_t)+
\frac{1}{2}\frac{\partial^2 g(t,r_t)}{\partial r_t^2}\sigma^2(t,r_t)-
r_tg(t,r_t)
=0
$$

\begin{align}
b(t,T)&=\frac{1}{\alpha}\left( 1-e^{-\alpha(T-t)}\right)  \\
a(t,T)&=\left(\mu-\frac{\sigma^2}{2\alpha^2}\right) (b(t,T)-T+t)-
  \frac{\sigma^2}{4\alpha}b^2(t,T) \\
P(t,T)&=e^{a(t,T)-b(t,T)r_t}
\end{align}

### Cox-Ingersoll-Ross

$$
dr_t = \alpha(\mu-r_t)dt + \sigma\sqrt{r_t}d\widetilde{W}_t
$$
Which gives the pde
$$
\frac{\partial g(t,r_t)}{\partial t}+
\frac{\partial g(t,r_t)}{\partial r_t}\alpha(\mu-r_t)+
\frac{1}{2}\frac{\partial^2 g(t,r_t)}{\partial r_t^2}\sigma^2(t,r_t)r_t-
r_tg(t,r_t)
=0
$$

\begin{align}
\gamma&=\sqrt{\alpha^2+2\sigma^2} \\
b(\tau)&=\frac{2\left( e^{\gamma\tau}-1\right)}
  {(\gamma+\alpha)\left( e^{\gamma\tau}-1\right)+2\gamma} \\
a(t,T)&=\frac{2\alpha\mu}{\sigma^2}
  ln\left(
    \frac{2\gamma e^{\frac{1}{2}(\gamma+\alpha)\tau}}
    {(\gamma+\alpha)\left( e^{\gamma\tau}-1\right)+2\gamma}
  \right) \\
  &=\frac{2\alpha\mu}{\sigma^2}
  ln\left(b(\tau)
    \frac{\gamma e^{\frac{1}{2}(\gamma+\alpha)\tau}}
    {\left( e^{\gamma\tau}-1\right)}
  \right) \\
P(t,T)&=e^{a(t,T)-b(t,T)r_t}
\end{align}

### Hull-White model

Very similar to Vasicek except the mean-reversion level is a deterministic function of time.
This means $\mu(t)$ can be chosen to match, as closely as possible, the exact yield curve.

$$
dr_t = \alpha(\mu(t)-r_t)dt + \sigma d\widetilde{W}_t
$$
Which gives the pde
$$
\frac{\partial g(t,r_t)}{\partial t}+
\frac{\partial g(t,r_t)}{\partial r_t}\alpha(\mu(t)-r_t)+
\frac{1}{2}\frac{\partial^2 g(t,r_t)}{\partial r_t^2}\sigma^2(t,r_t)-
r_tg(t,r_t)
=0
$$

\begin{align}
b(t,T)&=\int_t^Te^{-\int_t^s\alpha(u)du}ds \\
a(t,T)&=\int_t^T\left( -\alpha\mu(s)b(s,T)+
  \frac{1}{2}\sigma^2b^2(s,T)\right) ds \\
P(t,T)&=e^{a(t,T)-b(t,T)r_t}
\end{align}

## Summary

Model | Dynamics | $r_t>0$ for all $t$ | Distribution of $r_t$
:--- | :--- | :---: | :---
Vasicek | $dr_t = \alpha(\mu-r_t)dt + \sigma d\widetilde{W}_t$ | No | Normal
CIR | $dr_t = \alpha(\mu-r_t)dt + \sigma\sqrt{r_t}d\widetilde{W}_t$ | Yes | Non-central Cho-squared
Hull-White -- Vasicek | $dr_t = \alpha(\mu(t)-r_t)dt + \sigma d\widetilde{W}_t$ | No | Normal
Hull-White -- CIR| $dr_t = \alpha(\mu(t)-r_t)dt + \sigma\sqrt{r_t}d\widetilde{W}_t$ | Yes | Non-central Cho-squared

### Limitations

- Single-factor short-rate models mean all maturities behave in the same way. This means they are useless for pricing swaptions but OK for pricing caps and floors.
- There is little consistency in valuation between the models.
- They are difficult to calibrate.

One-factor models have further limitations

- Changes in the prices for bonds of different maturities are not perfectly correlated, as one would expect to see if a one-factor model was correct.
- Long-run historical data shows sustained periods of both high and low interest rates.
- This is important for long-term insurance pricing and asset-liability modelling.
- One-factor models can be useful for valuing simple liabilities with no option characteristics.
- It can be appropriate to address these deficiences with multi-factor models which may include a multi-dimensional Wiener.
