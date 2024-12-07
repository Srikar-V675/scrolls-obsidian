---
date: 2024-12-06
tags:
  - zettel
  - data-science
  - assignment
status: literature
publish: true
---
# Probability and Statistics Assignment

## Section-B Q2 Answers
**Dataset:**

| Name  | Adam | Bella | Charlie | David | Emily | Frank | Grace | Harry | Isabella | Jack |
| ----- | ---- | ----- | ------- | ----- | ----- | ----- | ----- | ----- | -------- | ---- |
| Score | 56   | 78    | 90      | 82    | 60    | 95    | 72    | 88    | 80       | 76   |

**Before doing any calculation we need to sort the data.**

| Name  | Adam | Emily | Grace | Jack | Bella | Isabella | David | Harry | Charlie | Frank |
| ----- | ---- | ----- | ----- | ---- | ----- | -------- | ----- | ----- | ------- | ----- |
| Score | 56   | 60    | 72    | 76   | 78    | 80       | 82    | 88    | 90      | 95    |

#### Problem: Calculate the mean score of the class. What does this tell you about the overall performance of the class?

**Formula:** $$\bar{x} = \frac{1}{n} \cdot \sum_{i=1}^n x_i$$

$$sum = 56+60+72+76+78+80+82+88+90+95 = 777$$

$$\bar{x} = \frac{777}{10} = 77.7$$

**Answer:** The mean is `77.7` and this tells us that the most common score scored by the entire class is `77.7`.

#### Problem: Calculate the median score of the class. How does it compare to the mean and what does this comparison tell you about the distribution of scores?

**Formula:** $$M =  \begin{cases}  x{\left[\frac{n+1}{2}\right]} & \text{if } n \text{ is odd} \\  \frac{x{\left[\frac{n}{2}\right]} + x{\left[\frac{n}{2} + 1\right]}}{2} & \text{if } n \text{ is even} \end{cases}$$

Since in our case $n$ is $even$ we need to use the 2nd formula to calculate the `median` of the dataset. 

$$M = \frac{x_5 + x_6}{2}$$

$$M = \frac{78+80}{2} = 79$$

**Answer:** The `median` is `79`. We can say that the distribution is `left-skewed` because the $\bar{x} < M$ i.e the most common marks in the class is lesser than the middle marks of the class.

#### Problem: Calculate the mode of the scores. What does this tell you about the most common score in the class?

**Formula:** $$mode = most\ frequent\ element\ in\ the\ data$$

**Answer:** Since all the marks are unique in this dataset all of the marks appear exactly once and hence there is no mode for this dataset.

#### Problem: Based on the mean, median, and mode you calculated, describe the performance of the class.

The mean score is `77.7` and the median is `79`. The median is slightly higher than the mean, indicating that the distribution is left-skewed which tells us that many of the students scored marks near to the `middle` value but due to some very low scores(like 56, 60) the average was brought down. 

Since this dataset has no mode and all the marks scored by the students is unique, the marks are evenly distributed without any score being more common than the others. The overall performance of the class is good with marks being more or less close to the average score. 

#### Problem: What could be the possible implications if the mode is significantly lower or higher than the mean and median?

The `mode` of a dataset gives us the marks that has the most occurrence in a dataset. 

1. If the mode is significantly lower than the `mean` and `median` then we can tell that there is a `subgroup` or `subgroups` of marks that are more frequent and way lesser than the `mean` and `median` hence bringing down the average of the class. This might mean that there is a `gap` in the performance of students and the frequency of poorly performing students is more.

2. If the mode is significantly higher than the `mean` and `median` then we can tell that there is a `subgroup` or `subgroups` of marks that are more frequent and way higher than the `mean` and `median` hence pushing up the average of the class. This might mean that there is a `gap` in the performance of students and the frequency of highly performing students is more.

In these cases where the `mode` is significantly lower or higher than the `mean` and `median`, it often hints at a dataset that has a **bimodal** or **multi modal distributions** where there are distinct performance subgroups in the data. This could be due to different study habits, gaps in understanding concept etc...