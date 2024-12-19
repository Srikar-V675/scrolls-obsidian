---
id: 1732806952-variance-wrt-probability
aliases:
  - variance-wrt-probability
tags:
  - zettel
  - data-science
date: 2024-11-28-Thu
publish: true
status: literature
---
# variance-wrt-probability

**Source:** [[variance|variance]]

[[variance|variance]] with respect to probability is when we need to include the [[expected probability values]] because now the [[mean]] will be the [[expected probability values]].

## Formulas

**Basic:** $$\mathrm{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]$$

> [!TIP]
> We want expected variance hence we have an `E` for expected, then what is [[variance|variance]]? $$(x - \bar{x})^2$$ hence we have that inside.

**Alternative Formula:** $$\mathrm{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$$

where,
-  $$E(X^2) = \sum x_i^2 P(X = x_i)$$
-  $$E(X) = \sum x_i P(X = x_i)$$

## Derivation

The variance can be expressed as:
$$\mathrm{Var}(X) = \mathbb{E}[(X - \mathbb{E}[X])^2]$$

Expanding that gives:
$$\mathrm{Var}(X) = E[X^2] - 2E[X]E[X] + (E[X])^2$$

This leads to the formula:
$$\mathrm{Var}(X) = \mathbb{E}[X^2] - (\mathbb{E}[X])^2$$

---
## Related Notes
[[expected probability values]]
[[variance|variance]]

## References(links)
[[Core ML and MLOPs]]
