---
id: 1733237113-conditional-probability
aliases:
  - conditional-probability
tags:
  - zettel
  - data-science
date: 2024-12-03-Tue
publish: true
status: literature
---
# conditional-probability

**Source:** [[probability]]

[[probability]] of an event `A` occurring given the `condition` that event `B` has `already` occurred.

> !EXAMPLE
> [[probability]] of `A` having `cancer` given that he already has a `tumour`.

**Notation:** $$P(A | B)$$ is probability of `A` occurring given `B` already occurred.

**Formula:** $$P(A | B) = \frac{P(A \cap B)}{P(B)}, \quad \text{when } P(B) > 0.$$

## Special cases
1. A & B are [[disjoint sets]]
$$P(A \cap B) = \emptyset$$

$$P(A | B) = \frac{P(\emptyset)}{P(B)} = \frac{0}{P(B)} = 0.$$

2. B subset of A 
whenever B happens A also happens. ex: probability of person having fever given that he already has dengue.

Since $$( B \subseteq A )$$, we have:

$$A \cap B = B.$$

Substituting this into the conditional probability formula gives:

$$P(A | B) = \frac{P(B)}{P(B)} = 1.$$

---
## Related Notes
[[disjoint sets]]
[[probability]]

## References(links)
[[Core ML and MLOPs]]
