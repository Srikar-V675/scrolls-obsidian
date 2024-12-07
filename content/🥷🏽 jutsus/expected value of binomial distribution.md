---
date: 2024-12-07
tags:
  - zettel
  - data-science
status: literature
publish: true
---
# expected value of binomial distribution

**Source:** [[binomial distribution]], [[expected probability values]]

**Formula:** $$\mathbb{E}[X] = n \cdot p$$

Where:
- $n$ is number of trials
- $p$ is [[probability]] of success

## Why is the formula like this?

Let's prove it by taking an example. Let's say we have:
- $n = 2$
- $p = 0.7$
- $(1-p) = 0.3$ 
- $success = 1$ and $failure = 0$

By [[expected probability values]] formula we get, 
$$\mathbb{E}[X] = (0\cdot 0.3 + 1\cdot0.7) + (0\cdot 0.3 + 1\cdot0.7) = 2 \cdot 0.7 = n \cdot p$$

---
## Related Notes
[[probability-distributions]]
[[expected probability values]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]