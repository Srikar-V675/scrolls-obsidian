---
date: 2024-11-06 00:06
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Recursion

### Summary
- Recursion is a method for solving computational problems where the solution to the problem depends on solutions of smaller instances of the problem.

> [!quote]
> "Recursion is defining a problem in terms of smaller versions of itself"

**Three Parts:** A recursion problem has 3 parts
1. Base Case: solution to the simplest possible problem.
2. Work towards Base case: for any problem the base case is the final goal.
3. Recursive call: calling ourselves where each call solves the problem on a smaller version but on the same algorithm or code.

> [!tip]
> Consider recursion as having a weird gift box that contains a solution to your problem, but when you open the box you have many other boxes. There are 2 types of boxes:
> 1. Box that contains other boxes a.k.a `Recursive boxes`
> 2. Box that contains a value a.k.a `Base case box`<br>
> **Whenever you are solving a seemingly recursive problem, follow these 2 steps:**
> Step-1: Recognise base case and recursive case
> Step-2: Map out a decision tree for the recursive calls<br>

![[Recursion-Boxes-Tree-Example.excalidraw.png]]

### Tail Recursion
It is a recursive function in which the last statement executed by the function is the recursive call after this there is no other statement to execute.

> [!example]
> ```python
> def prints(n):
> 	if (n < 0):
> 		return
> 	print("n:", n)
> 	prints(n-1)
> prints(4)
> ```
> In the example above the last statement executed by the function is the recursive call hence this function is a `tail-recursion.`

#### Why is tail-recursion optimal?
- Tail-recursive functions can be `optimised` by the `compiler`.
- Compilers use a `[[[[stack]]]]` to execute recursive procedures. Every time a recursive procedure is `called` the compiler `pushes` the recursive call with the arguments to the [[Stack]] (also adds the no. of statements to execute after recursive call). After a recursive call has `finished execution` it is `popped` out.
- This usually leads to `more [[stack]] depth` in case of `non-tail-recursive functions`.
- Some programming languages implement `tail-call-optimisation - TCO` which leads to constant auxiliary space instead of the usual O(N).

#### Example:

**Factorial:** We all know the recursive function for solving factorial of a number.

```python
def fact(n):
	if n == 0:
		return 1
	return n * fact(n-1)
print(fact(5))
```

- But this is not a tail-recursive-function. Even though, it looks like the last statement executed is the recursive call but the thing is after we get the output of fact(n-1) it has to multiplied with n to get out final output. Hence, it makes this function non-tail-recursive.

![[Recursion-fact-non-tail.excalidraw.png]]

- Instead of multiplying n with factorial of n-1 which leads to non-tail-recursion, we can calculate the factorial at each step and store it in a extra variable which can be returned directly.

```python
def fact_tail(n, acc = 1):
	if n == 0:
		return acc
	return fact_tail(n-1, n*acc)
print(fact_tail(5))
```

- In this case there is no statement to be executed after the recursive call. Hence this makes it tail-recursive, that is there is no need of a [[Stack]] trace cause the output is computed and passed at every step.

![[Recursion-fact-tail.excalidraw.png]]

> [!note]
> Python doesn't support `Tail-Call-Optimisation(TCO)` hence it still creates a [[Stack]] trace for the non-tail-recursive-function we wrote in Python above. This is the reason why we have used the line`return fact_tail(n-1, n*acc)` as it needs to return the result to previous calls.

### Memoization
In some cases, you may be computing the result for previously computed inputs. Let's look at the Fibonacci example again. `fib(5)` calls `fib(4)` and `fib(3)`, and `fib(4)` calls `fib(3)` and `fib(2)`. `fib(3)` is being called twice! If the value for `fib(3)` is memoized and used again, that greatly improves the efficiency of the algorithm and the time complexity becomes O(n).

### Essential Qs
- [Generate Parenthesis](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Recursion/Medium/1.%20Generate%20Parenthesis.md#L4)
- [Combinations](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Recursion/Medium/2.%20Combinations.md#L4)
- [Subsets](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Recursion/Medium/3.%20Subsets.md#L4)

---
## Tasks
- [ ] Create independent zettels

## Key Terms
- **Recursion:** defining a problem in terms of smaller versions of itself
- **Base Case:** the simplest version of a problem that can compound to give you the result of a bigger problem
- **Recursive Call:** the call to itself but with a smaller version of the current problem
- **Tail Recursion:** recursive function in which the last statement is the recursive call
- **Tail Call:** the recursive call as the last statement in `tail-recursive-functions`
- **TCO - Tail Call Optimisation:** some programming languages optimise the tail calls by not constructing the [[Stack]] trace leading to constant auxiliary space used by the recursive-function

## Related Notes
- [[Arrays]]
- [[Strings]]
- [[Quick Sort]]
- [[Merge Sort]]

## References(links)
- [Recursion cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/recursion/)
- [Programming - Recursion](https://users.cs.utah.edu/~germain/PPS/Topics/recursion.html)
- [Tail Recursion - Section 2 and Homework 2 | Coursera](https://www.coursera.org/lecture/programming-languages/tail-recursion-YZic1)
- [Recursion for Beginners - Fibonacci Numbers - YouTube](https://www.youtube.com/watch?v=dDokMfPpfu4&t=391s)
- [What is Tail Recursion - GeeksforGeeks](https://www.geeksforgeeks.org/tail-recursion/)
- [ChatGPT | Clarification of return statement & TCO in Python](https://chatgpt.com/share/71be8e68-5b1a-47e8-a0ad-636b931a6202)