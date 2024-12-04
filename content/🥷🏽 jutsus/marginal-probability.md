---
id: 1733236288-marginal-probability
aliases:
  - marginal-probability
tags:
  - zettel
  - data-science
date: 2024-12-03-Tue
publish: true
status: literature
---
# marginal-probability

**Source:** [[probability]]

Let's consider a [[joint-probability-distribution|joint-probability-distribution]]. 

|       | cats | fish | dogs |     |
| ----- | ---- | ---- | ---- | --- |
| men   | 2    | 4    | 6    | 12  |
| women | 5    | 3    | 2    | 10  |
|       | 7    | 7    | 8    | 22  |

In the above table the [[joint-probability-distribution]] is of the gender and the pets they like. marginal-probability is nothing but when you get the [[probability]] of either `X`(gender) or `Y`(pets) when they are independent of the other. 

Let's take marginal-probability of `pets` independent of `gender`.
-  people who prefer `cats` = 7 & probability would be $$\frac{7}{22}$$

Just like that we can do for vice-versa also. See the table and I think you would get it.

---
## Related Notes
[[joint-probability-distribution]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]
