---
date: 2024-11-05 03:00
sources: "[[Arrays]]"
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Intervals

Intervals are just an extension of [[Arrays]] problems, where we have an array that contains intervals in the format `[start, end]`. 

So the input will look like this: 
```python
input = [[1,2],[2,3],[4,5], ...]
```

We will be performing operations on these intervals where first index is `start` and second index is `end`.

> [!tip]-
> Clarify with the interviewer whether `[1, 2]` and `[2, 3]` are considered overlapping or not. 
> Also clarify whether `[a, b]` interval follows `a<b` always.

> [!tip]+
> Use number lines to represent intervals when working these kind of problems.


### Techniques
- Sorting the intervals by the starting index(or start of interval)
- Check if overlapping intervals 
- Merge overlapping intervals

### Essential Qs
- [[merge intervals]]


---
## Related Notes
[[Arrays]]

## References(links)
[interval-cheatsheet-for-coding-interviews-tech-interview-handboo](https://omnivore.app/srikarv/interval-cheatsheet-for-coding-interviews-tech-interview-handboo-1921f014dc3)