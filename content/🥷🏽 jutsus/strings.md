---
date: 2024-11-06 00:11
sources: 
tags:
  - zettel
  - dsa
status: literature
publish: true
---
# Strings

### Summary
Very similar to [[Arrays]] because they are sequence of characters while [[Arrays]] are sequence of a single data type.

### Common Things
Common `data structures` for looking up strings
	- Trie/Prefix tree
	- Suffix tree

Common `algorithms` for searching substrings
	- Rabin-Karp Algorithm
	- KMP

### Time Complexity
| Operation | Big-O |
| --------- | ----- |
| Access    | O(1)  |
| Search    | O(n)  |
| Insert    | O(n)  |
| Remove    | O(n)  |

#### Operations Involving Another String

| Operation                                       | Big-O    | Note                                                                                                                                                                                          |
| ----------------------------------------------- | -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Find substring                                  | O(n.m)   | This is the most naive case. There are more efficient algorithms for string searching such as the [KMP algorithm](https://en.wikipedia.org/wiki/Knuth%E2%80%93Morris%E2%80%93Pratt_algorithm) |
| Concatenating strings                           | O(n + m) |                                                                                                                                                                                               |
| Slice                                           | O(m)     |                                                                                                                                                                                               |
| Split (by token)                                | O(n + m) |                                                                                                                                                                                               |
| Strip (remove leading and trailing whitespaces) | O(n)     |                                                                                                                                                                                               |

### Techniques
Counting characters
String of unique characters
Anagram
Palindrome

### Essential Qs
[Valid Anagram](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/9.%20Valid%20Anagram.md#L4)
[Valid Palindrome](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Easy/10.%20Valid%20Palindrome.md#L4)
[Longest Substring without repetitions](https://github.com/Srikar-V675/DSA-Problems/blob/0c573923a912f903467d06e646b0a266d4e06d7b/Arrays%20%7C%20Strings/Medium/10.%20Longest%20Substring%20without%20repetitions.md#L4)

---
## Questions
Are Rabin-Karp and KMP asked in interviews? Are they important algorithms?

How does a trie work?

## Related Notes
[[Arrays]]

## References(links)
[String cheatsheet for coding interviews | Tech Interview Handbook](https://www.techinterviewhandbook.org/algorithms/string/)
