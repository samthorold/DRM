
# Binomial Model

The binomial model is one of the simplest and most flexible methods of option
pricing.

```julia
function recursive_tree(T, t, h, S, K, σ, δ, r, payoff, eu=true)
    exercise_value = payoff(S, K)
    # if t==T, node is a leaf node and exercise
    if round(t, 6)==T
        return exercise_value
    end
    # otherwise, discount the up and down values
    u = _u(h, σ, δ, r)
    d = _d(h, σ, δ, r)
    q = _q(h, u, d, δ, r)
    Cu = recursive_tree(T, t+h, h, S*u, K, σ, δ, r, payoff, eu)
    Cd = recursive_tree(T, t+h, h, S*d, K, σ, δ, r, payoff, eu)
    continuation_value = exp(-r*h) * (q*Cu + (1-q)*Cd)
    if !eu
        return max(exercise_value, continuation_value)
    end
    return continuation_value
end
```
