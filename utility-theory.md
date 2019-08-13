
# Utility theory

All part of _theories of financial market behaviour_.

- Rational expectations theory -- EMH
- **Rational choice -- Utility theory**
- Behavioural finance

**Utility**: Satisfaction an individual obtains from a particular course of
action.
It is a numerical value that can be assigned to each possible value
of an investor's wealth through a utility function.
Individuals act in a way that maximises $U(W)$.

## Axioms

There are four common axioms;

- _Comparability_: An investor can state a preference for all certain outcomes
- _Transitivity_: if $A>B$ and $B>C$ then $A>C$.
- _Independence_: If an investor is indifferent between $A$ and $B$,
they are also indifferent between; $A$ with liklihood $p$ and $C$ with
liklihood $1-p$, and $B$ with liklihood $p$ and $C$ with liklihood $1-p$.
- _Certainty equivalence_: If $A>B$ and $B>C$, there is a unique $p$ such that
an investor is indifferent between; $A$ with liklihood $p$ and $C$ with
liklihood $1-p$, and $B$.

Investors' preferences are assumed to be influenced by risk.
What does a utility function say about an investor's risk-return preference?

## Utility functions and risk preference

Investors are assumed to be non-satiated, $U'(W)>0$,
and risk-averse, $U''(w)<0$.
This means they prefer more to less and value a decrease in risk more than an
increase in risk of the same amount.

But how does an investor's risk aversion change with the level of wealth?

Absolute risk aversion measures an investor's aversion to risk.
Relative risk aversion measures an investor's aversion to risk relative to
their wealth.
$$
A(w)=-\frac{U''(w)}{U'(w)}
$$
$$
R(w)=-w\frac{U''(w)}{U'(w)}=wA(w)
$$

## Forms of utility function

Three common forms of utility function are;

- Quadratic: $U(w)=a+bw+cw^2$ or $U(w)=w+dw^2$ (where $d<0$)
$$
A(w)=-\frac{2d}{1+2dw} \text{ and } A'(w)=\frac{4d^2}{(1+2dw)^2}>0
$$
$$
R(w)=-\frac{2dw}{1+2dw} \text{ and } R'(w)=-\frac{2d}{(1+2dw)^2}>0
$$
The quadratic utility function has increasing absolute and relative risk
aversion.

- Log: $U(w)=ln(w)$
$$
A(w)=\frac{1}{w} \text{ and } A'(w)=-\frac{1}{w^2}<0
$$
$$
R(w)=1 \text{ and } R'(w)=0
$$
The log utility function has decreasing absolute and constant relative risk
aversion.
While an investor is less concerned with the absolute value of risk as their
wealth increases, the value of risk remains a constant percentage of their
wealth.

- Power: $U(w)=\frac{w^\gamma -1}{\gamma}$
$$
A(w)=-\frac{\gamma -1}{\gamma} \text{ and } A'(w)=\frac{\gamma -1}{\gamma^2}<0
$$
$$
R(w)=-(\gamma -1) \text{ and } R'(w)=0
$$
The power utility function is one of a wider class of hyperbolic absolute
risk aversion functions.
$\gamma$ is the risk aversion coefficient.
The power function has decreasing absolute and constant relative risk
aversion.
While an investor is less concerned with the absolute value of risk as their
wealth increases, the value of risk remains a constant percentage of their
wealth.

None of the utility functions above allow much freedom to calibrate
the function to reflect individual investor preferences.
Further, it may not be possible to model utility over all levels of wealth
with a single function.

## State-dependent utility functions

State-dependent utility functions can be used to model changes in the
utility functions at different levels of wealth.
For example, a firm will be highly risk averse at levels of wealth close to
insolvency.
States for individuals that may influence the form of a utility functions
could be healthy/sick or married/single.

To construct a utility function in practice,
we may ask individuals a series of questions and try to fit a line to their
answers, keeping in mind the axioms and principles of non-satiation and
risk-aversion.

## Maximising utility with insurance

Buying insurance will diminish the wealth of an individual,
but it may increase utility.
A risk-averse person will pay more for insurance than the long-run
average value of claims.
This means buying insurance is worthwhile for the individual
even if the insurer adds a premium to the expected value of claims
to make a profit.
An insurance contract is feasible if the minimum premium the insurer is
willing to offer less than the maximum premium the individual is willing to
pay for insurance.

The maximum premium, $P$, an individual is willing to pay to insure
against a random loss, $X$, is given by
$$
E[U(a-X)]=U(a-P)
$$
where $a$ is the initial level of wealth.

The minimum premium, $Q$, an insurer is willing to offer to insure
a random loss, $X$, is given by
$$
E[U(a+Q-X)]=U(a)
$$
where $a$ is the initial level of wealth.

## Limitations

Expected utility is good at focusing us on the trade-offs involved in risky
decisions.
But;

- Calculating expected utility is hard. What is the shape of someone's
utility function?
Normally we have to settle for modelling a general feature such as risk
aversion
- Applying to several sets of risky decisions is hard.
- Considering the utility function of a firm is even harder than that of an
individual.

Expected utility theory is not good at modelling interdependence of risks.

## Alternative decision rules

- Mean-variance
- Stochastic dominance
- Behavioural finance -- non-rational investment behaviour

