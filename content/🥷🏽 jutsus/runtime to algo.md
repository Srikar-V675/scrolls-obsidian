---
date: 2024-11-05 23:35
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Runtime to Algo 

How long an algorithm takes to execute given the input size. It is also called the `time complexity`. It gives us the upper bound of runtime in the worst case scenario. It is important because it helps us compare algorithms without actually running them for `large input sizes`.

### Rules
There are some rules to be followed when writing this notation.

**Rule-1:** Highest degree of the equation is only considered. (worst case)

> [!example]
> O(n^2 + n.log n + n) becomes O(n^2)

**Rule-2:** Constants are ignored.

> [!example]
> O(2n) or O(n/2) is equal to O(n) even though the first one is bigger. 

### Famous Big-O's

There are some Big-O time or space complexities that often appear in most of the algorithms or code we write.

![[big-o-notation.png]]

The best one or the most fastest is O(1) while O(n!) is the slowest. When we write code we always try to write the algorithm with fastest time or space complexities and Big-O plays a good role to denote that.

### $O(1)$
Constant time or space complexity.
> [!example]
> **[[Arrays]]:**
> - lookup
> - push to end
> - pop from end
> 
> **HashMap:**
> - lookup
> - insert
> - remove

### $O(\log n)$
Logarithmic time or space complexity. When input size decreases by half at each step, then the problem is O(log n).

`2^x = n` , x is number of times the input size must be decreased by half to get single element. To find x we can apply log on both sides, `x = log2 n`
> [!example]
> - **[[Binary Search]]**
> - **Heap:**
> 	- push
> 	- pop

### $O(n)$
Linear time or space complexity.

The most common time complexity when dealing with [[Arrays]] or [[Strings]].
> [!example]
> - **Looping**
> - **Linear Search**
> - **Build Heap**
> - **Monotonic [[Stack]] or Sliding Window**

### $O(sqrt(n))$
Not very common complexity

> [!example]
> **Finding all factors of n**

### $O(n^2)$
Squared time or space complexity.

Occurs when we loop through the 1d array for every single element in the 1d array which makes it `n * n` times.

Also common when traversing a 2d array or matrix and some sorting algorithms on 1d array.

> [!example]
> - **Traverse a matrix**
> - **Pair of elements in array**
> - **Insertion, Bubble, Selection Sort**

## $O(K \cdot \log{n})$

$K$ times of logarithmic. Occurs when `K heap push/pop` and `K Binary searches`.

### $O(n \cdot \log n)$
Linear log time or space complexity. `log n` occurs when we decrease the input size by half at each step, if this single step is applied n times then it becomes O(n.log n).

> [!example]
> - **Heap Sort**
> - **[[Quick Sort]]**
> - **[[Merge Sort]]**
> - **[[Tim Sort]]**

### $O(2^n)$
The complexity where at each step the input size increases by progressive power of 2. Recursion, combinatoric or backtracking. It requires memoization to reduce repetitive tasks.

> [!example]
> ![[O(2^n).png]]
> **Binary [[Trees]]**

### $O(c^n)$
The complexity where at each step the input size increases by progressive power of c. 
[[Trees]] with more than 2 child nodes at each step in recursion or backtracking.

### $O(n!)$
The worst possible time or space complexity. Recursion, Combinatoric or backtracking. It requires memoization to reduce repetitive tasks.

> [!example]
> - **Permutations**
> - **Travelling Salesman Problem**

## Amortized Time Complexity

Once in a while you do a costly operation. It is done so rarely that the costly task is diluted. 

> [!example]
> We have done $N \cdot O(1)$ operations and one $O(N)$ costly task then `TC` -> $O(N)$ and not $O(N^2)$

---
## Related Notes
[[DSA Mastery]]

## References(links)
[Big-O Notation - For Coding Interviews - YouTube](https://youtu.be/BgLTDT03QtU)
[NeetCode Big-O Notation](https://neetcode.io/courses/lessons/big-o-notation)
