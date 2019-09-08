
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
