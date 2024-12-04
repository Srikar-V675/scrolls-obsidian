---
id: 1732847787-covariance
aliases:
  - covariance
tags:
  - zettel
  - data-science
date: 2024-11-29-Fri
publish: true
status: literature
---
# covariance

**Source:** [[variance|variance]]

> `co` <-> `relationship`

Covariance is nothing but the relationship between two diffferent entities or [[content/🥷🏽 jutsus/random variables.md|random variables]]. 

The relationship gives us the `proportionality` between the variables.

## Formula
**Sample Covariance:** $$cov(X, Y) = \frac{1}{n-1} \sum_{i=1}^{n} (x_i - \bar{x}).(y_i - \bar{y})$$

**Population Covariance:**  $$cov(X, Y) = \frac{1}{N} \sum_{i=1}^{N} (x_i - \mu{x}).(y_i - \mu{y})$$

> [!IMPORTANT]
> Covariance only gives us the `direction` of relationship between two [[content/🥷🏽 jutsus/random variables.md|random variables]] and not the `strength`.

$$cov(X, Y) > 0$$ - +ve relationship
$$cov(X, Y) < 0$$ - -ve relationship
$$cov(X, Y) = 0$$ - near 0 relationship

![[covariance-graphs.png]]

---
## Related Notes
[[variance|variance]]
[[content/🥷🏽 jutsus/random variables.md|random variables]]
[[content/🥷🏽 jutsus/statistics.md|statistics]]

## References(links)
[[content/🥷🏽 jutsus/Core ML and MLOPs.md|core ML and MLOPs]]
