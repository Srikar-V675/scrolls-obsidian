---
date: 2024-11-06 00:01
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Matrix

## Summary
- A matrix is a 2D array. Problems related to matrix usually involve: DP or graph traversal. In this note we will discussing about problems that come under matrix operations and not DP or graph traversal.

### Techniques
#### Creating an empty NxM matrix
We often need to create an empty matrix of the same size as the original matrix to store visited states or the DP table.

> [!tip]
> ```python
> empty_matrix = [[0 for _ in range(len(matrix[0])) ] for _ in range(len(matrix))]
> ```

#### Copying the Matrix
We also need to copy the original matrix to make changes in it and experiment without changing the original matrix.

> [!tip]
> ```python
> copied_matrix = [ row[:] for row in matrix ]
> ```

#### Transposing Matrix
There are operations on matrices that benefit from transposing the matrix. For many grid-based games it can be modelled as a matrix. Often to check the winning condition of the current state of game, we need to do it both horizontally and vertically, instead of writing code for verifying both horizontally and vertically we can write the code for horizontally only and then transpose the matrix to reuse the horizontal verification code.

> [!tip]
> ```python
> transpose = zip(*matrix)
> ```

### Essential Qs
- [Set Matrix Zeroes](https://github.com/Srikar-V675/DSA-Problems/blob/17caa0a470a55f70437451878da0dfacbeb57e45/Arrays%20%7C%20Strings/2D%20Array/1.%20Set%20Matrix%20Zeroes.md)
- [Spiral Matrix](https://github.com/Srikar-V675/DSA-Problems/blob/17caa0a470a55f70437451878da0dfacbeb57e45/Arrays%20%7C%20Strings/2D%20Array/2.%20Spiral%20Matrix.md)

## Tasks
- [ ] Create permanent zettel

---
## Key Terms
- **Transpose:** Converting rows to columns and columns to rows in a matrix.

## Related Notes
- [[Arrays]]

## References(links)
[Matrix cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/matrix/)
