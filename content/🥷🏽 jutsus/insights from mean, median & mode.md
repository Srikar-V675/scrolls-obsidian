---
date: 2024-12-06
tags:
  - zettel
  - data-science
status: literature
publish: true
---
# insights from mean, median & mode

**Source:** [[measures of central tendency]]

Things we need to keep in mind is that:
1. [[mean]] is the `most common`element in the dataset.
2. [[median]] is the `middle` element in the dataset.
3. [[mode]] is the `most frequent` element in the dataset.

## Points
- if [[mean]] is almost same as [[median]] then the data has a symmetric distribution because the most common element is near to the middle element of the dataset. 
	- if the [[mean]] is more then [[median]] then that means the data is `right-skewed` because the most common element is greater than the middle element and vice versa (left-skewed). 
	- If the difference is extreme then it can mean that the most common element([[mean]]) is at the extremes on either side hence being influenced by outliers.
- if [[mode]] is significantly lesser or higher than the [[mean]] and [[median]] then there could be chances of having a `bimodal` or `multi-modal` distribution which is nothing but subgroup or subgroups with more frequent elements that influence the [[mean]] of the dataset. 
	- If the [[mode]] is significantly lesser than the [[mean]] and [[median]] then that means that there is a subgroup or subgroups of data that are highly frequent and less than the [[mean]] giving rise to a gap in the dataset. 
	- In this case the gap indicates that the frequency of lesser elements is more.

---
## Related Notes
[[probability & statistics assignment]]
[[measures of central tendency]]

## References(links)
[[Core ML and MLOPs]]