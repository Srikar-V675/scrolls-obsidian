---
date: 2024-12-07
tags:
  - zettel
  - data-science
status: literature
publish: true
---
# binomial distribution

**Source:** [[probability-distributions]], [[binomial coefficient]]

It is a [[probability-distributions]] that models the number of successes in a ==fixed number of independent trials== of a ==binary experiment==(yes/no, heads/tails ...). The [[probability]] of success remains constant throughout the experiments. 

By independent trials it means that the outcome of one trial is not dependent on another trial. The [[random variables]] is the number of successes in a fixed number of trials. 

It is closely related to [[binomial coefficient]] because of the fact that we need `k` successes from a set of `n` trials, which is similar to [[binomial coefficient]]. 

Why do we need [[binomial coefficient]]?
Because we need to be able to get `k` successes without regard for the ordering of successes, if we do so without [[binomial coefficient]] then we would end up calculating for only one of the possibilities.

**Formula:** $$P(X=k) = \binom{n}{k} \cdot p^k \cdot (1-p)^{n-k} = \frac{n!}{k!(n-k)!} \cdot p^k \cdot (1-p)^{n-k}$$

Where:
- $\binom{n}{k}$ is [[binomial coefficient]]
- $p$ is [[probability]] of success
- $(1-p)$ is [[probability]] of failure

The formula can be read as: `(no. of ways of getting k success) * (total probability of k success) * (total probabilty of {n-k} failures)`

![[binomial distribution.png]]

---
## Related Notes
[[probability-distributions]]
[[binomial coefficient]]
[[probability]]
[[random variables]]
[[expected value of binomial distribution]]

## References(links)
[[Core ML and MLOPs]]