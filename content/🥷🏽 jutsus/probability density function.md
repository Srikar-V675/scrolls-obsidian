---
id: probability density function
aliases:
  - PDF
  - Probability Density Function
tags:
  - zettel
  - data-science
date: 2024-11-25 07:21
publish: true
sources:
  - "[[random variables]]"
status: literature
---
# Probability Density Function

It is a function that gives the [[probability]] of a given set of [[continuous random variables]] taking on a particular value.

#### Key Properties
- `Non-negativity`: $$f(x)\ >=\ 0$$
- `Normalization`: total area under the curve is always equal to 1. $$\int_{-\infty}^{\infty} f(x) \, dx = 1$$
- `Probability Calculation`: you can calculate the PDF of a [[continuous random variables]] falling within the range of [a, b] by using $$P(a \leq X \leq b) = \int_{a}^{b} f(x) \, dx$$

> [!tip]-
> $$f(x)$$ usually varies depending on the `PDF` and situation.

---
## Related Notes
[[random variables]]
[[continuous random variables]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]
