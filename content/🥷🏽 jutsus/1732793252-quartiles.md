---
id: 1732793252-quartiles
aliases:
  - quartiles
tags:
  - zettel
date: 2024-11-28-Thu
publish: true
status: literature
---
# quartiles

**Source:** [[content/🥷🏽 jutsus/1732792901-quantiles.md|quantiles]]

Divides the ditribution into 4 parts hence the name `quartiles`. 

> [!TIP]
> We just said that we are spliting the data into 4 parts but there are 3 quartiles. The reason is simple: 
> ```text
> P1 | P2 | P3 | P4
>   Q1   Q2   Q3
> ```

## Q1
**Formula:** $$n * \frac{1}{4}$$

-  [[content/🥷🏽 jutsus/median.md|median]] of the lower half of the data.

## Q2
**Formula:** $$n * \frac{2}{4}$$

-  [[content/🥷🏽 jutsus/median.md|median]] of the entire data

## Q3
**Formula:** $$n * \frac{3}{4}$$

- [[content/🥷🏽 jutsus/median.md|median]] of the upper half of data

## Interquartile range(IQR)
**Formula:** $$Q3 - Q1$$

-  gives us the majority/spread of the ditribution of data
-  data inside of this range is considered resistant to outliers and data outside of this range are the outliers.

---
## Related Notes
[[content/🥷🏽 jutsus/1732792901-quantiles.md|quantiles]]

## References(links)
[[content/🥷🏽 jutsus/Core ML and MLOPs.md|core ML and MLOPs]]
