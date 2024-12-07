---
date: 2024-12-07
tags:
  - zettel
  - data-science
status: literature
publish: true
---
# Poisson distribution

**Source:** [[probability-distributions]]

It is a [[probability-distributions]] that models the number of times of an event occurring in a given ==interval (time, volume or area)== given that the events happen independent of each other and at a constant average rate ($\lambda$).

[[poisson distribution]] doesn't have a set specific number of trials like [[binomial distribution]], because the event can occur randomly and continuously within that `interval` and the number of events is not exactly fixed. 

> [!example]
> Imagine a call center where, on average, 2 calls come in every minute (λ= 2 calls/min). You don’t know exactly how many calls will come in the next minute, but you know that, on average, you'll get 2 calls per minute. You can use the Poisson distribution to calculate the probability of getting, say, **exactly 3 calls** in the next minute.

**Formula:** $$P(X = k) = \frac{\lambda^k \cdot e^{-\lambda}}{k!}$$
 
---
## Related Notes
[[probability-distributions]]
[[binomial distribution]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]