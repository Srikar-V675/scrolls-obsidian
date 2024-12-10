---
date: 2024-12-04 
tags:
  - zettel 
  - data-science
status: literature
publish: true 
---
# normal distribution

**Source:** [[probability-distributions]]

It is is a `bell-shaped curve`, that is symmetric around the mean. This kind of distribution tells us that the [[mean]] has the highest [[probability]] of occurring and the values to the left of [[mean]] and right of [[mean]]'s [[probability]]s uniformly `decrease` on both sides. I'm sure you would understand if you see the graph. 

> [!important]
> [[normal distribution]] is only applicable to [[continuous random variables]] and hence it is a [[probability density function]].

> [!important]
> [[normal distribution]] shows that the data near the [[mean]] are more frequent to occur than data away from the [[mean]].

![[normal distribution.png]]

## Data is normally distributed if
1. [[mean]] = [[median]] = [[mode]]
2. symmetric at centre 
3. 50% of values are to the left of [[mean]] and 50% of values are to the right of [[mean]].

[[normal distribution can be described by 2 parts]]

**Formula:** $$f(x) = \frac{1}{\sigma \sqrt{2\pi}} \exp^{-\frac{(x - \mu)^2}{2\sigma^2}}$$

> [!example]
> Race finishing times in F1 racing can be modelled as a [[normal distribution]]

---
## Related Notes
[[probability-distributions]]
[[mean]]
[[median]]
[[mode]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]