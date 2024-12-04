---
id: 1732806124-variance
aliases:
  - variance
tags:
  - zettel
  - data-science
date: 2024-11-28-Thu
publish: true
status: literature
---
# variance

**Source:** [[content/🥷🏽 jutsus/statistics.md|statistics]]

> `variance` <-> `varying`

Variance is measuring how much the data is spread out with respect to the common value([[content/🥷🏽 jutsus/mean.md|mean]]) in the data.

## Formulas
**Basic:** $$V(x) = \sigma^2$$
where, 
$$\sigma$$ is [[standard-deviation|standard-deviation]]

**Sample Variance:** $$s^2 = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x})^2$$

**Population Variance:** $$\sigma^2 = \frac{1}{N} \sum_{i=1}^{N} (x_i - \mu)^2$$

**Q:** Why `n-1` in sample variance?
**A:** You still don't know why.

---
## Related Notes
[[content/🥷🏽 jutsus/statistics.md|statistics]]

## References(links)
[[content/🥷🏽 jutsus/Core ML and MLOPs.md|core ML and MLOPs]]
