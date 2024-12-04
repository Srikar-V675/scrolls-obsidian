---
tags:
  - zettel
  - data-science
date: 2024-12-04-Wed
publish: true
status: literature
---
# uniform-distribution

**Source:** [[probability-distributions|probability-distributions]]

As the name says the [[content/🥷🏽 jutsus/probability.md|probability]] [[random variables]] both [[continuous random variables]] and [[discrete random variables]] is constant for all possible values of `x`.

![[uniform-distribution-graph.excalidraw.svg]]

## Formulae

we know,
$$area = b \cdot l$$

In above diagram,
$$b = (b - a)$$
$$l = f(x) = P(X)$$

So now area is $$area = (b-a) \cdot f(x)$$

then $$f(x) = P(x) = \frac{1}{(b-a)}$$

The `probability distribution function` is given by 
$$
f(x) =  \begin{cases}  \frac{1}{b-a} & \text{for } a \leq x \leq b \\  0 & \text{otherwise} \end{cases}
$$

> [!note]
> All of these `formulae` above is applicable to only [[continuous random variables]]

## Example problems
[[uniform-distributions-problems]]

---
## Related Notes
[[probability-distributions]]
[[probability]]
[[statistics]]

## References(links)
[[Core ML and MLOPs]]
