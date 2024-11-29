---
tags:
  - zettel
  - data-science
date: 2024-11-25 12:16
publish: true
sources:
  - "[[probability]]"
  - "[[random variables]]"
status: literature
---
# Expected Probability Values

It is the `mean value` of a [[probability]] distribution([[random variables]]) before any data is present(i.e before any experiment is done).

It represents the average result of many trials([[law of large numbers]]) of a random experiment.

**Formula:** $$\mathbb{E}[X] = \sum_{x} x P(X = x)$$

> [!important]+
> The [[expected probability values]] in [[law of large numbers]] comes from this value itself. Why does [[law of large numbers]] hold true? A: as you increase the number of experiments, the chances of each possible value occurring equally becomes high and hence average value -> expected value. 

![[expected-probability-value.excalidraw.svg]]

The above image tells us how [[law of large numbers]] holds true when the there equal occurrences of outcomes of a experiment(high likely to occur when experiment size is large)

---
## Related Notes
[[random variables]]
[[law of large numbers]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]
