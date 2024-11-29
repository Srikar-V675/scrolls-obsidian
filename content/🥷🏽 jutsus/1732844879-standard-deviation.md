---
id: 1732844879-standard-deviation
aliases:
  - standard-deviation
tags:
  - zettel
  - data-science
date: 2024-11-29-Fri
publish: true
status: literature
---
# standard-deviation

**Source:** [[content/🥷🏽 jutsus/1732806124-variance.md|variance]]

Standard deviation is just the `square root` of [[content/🥷🏽 jutsus/1732806124-variance.md|variance]]. Standard deviation is just another way of calculating the spread of data from the [[me[[content/🥷🏽 jutsus/mean.md|mean]].

***Formula:** $$\sigma = \sqrt{V(X)} = \sqrt{\sigma^2}$$

> [!IMPORTANT]
> We need to use [[content/🥷🏽 jutsus/1732844879-standard-deviation.md|standard-deviation]] when let's say we are trying to find [[content/🥷🏽 jutsus/1732806124-variance.md|variance]] for a metric unit like `metres` or something. Why? below

When we use [[content/🥷🏽 jutsus/1732806124-variance.md|variance]] to calculate the spread of data for a metric unit like `metres` then the variance will be in $$metres^2$$ because of the squaring to get rid of -ve values, but in therms of units `metres` and $$metres^2$$ are not same hence we use [[content/🥷🏽 jutsus/1732844879-standard-deviation.md|standard-deviation]] in these situations.

---
## Related Notes
[[content/🥷🏽 jutsus/1732806124-variance.md|variance]]
[[content/🥷🏽 jutsus/mean.md|mean]]
[[content/🥷🏽 jutsus/statistics.md|statistics]]

## References(links)
[[content/🥷🏽 jutsus/Core ML and MLOPs.md|core ML and MLOPs]]
