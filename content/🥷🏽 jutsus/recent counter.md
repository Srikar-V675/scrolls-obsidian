---
aliases:
  - leetcode 933
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[queue]]"
difficulty: easy
companies: 
publish: true
---

**DSA-PATTERNS:** [[queue]]

**DIFFICULTY:** easy

**COMPANIES:**

# Problem Description

**Leetcode Link:** [Number of Recent Calls - LeetCode](https://leetcode.com/problems/number-of-recent-calls/description/)

**Solution Link:** None

You have a `RecentCounter` class which counts the number of recent requests within a certain time frame.

Implement the `RecentCounter` class:

- `RecentCounter()` Initializes the counter with zero recent requests.
- `int ping(int t)` Adds a new request at time `t`, where `t` represents some time in milliseconds, and returns the number of requests that has happened in the past `3000` milliseconds (including the new request). Specifically, return the number of requests that have happened in the inclusive range `[t - 3000, t]`.

It is **guaranteed** that every call to `ping` uses a strictly larger value of `t` than the previous call.

**Example 1:**

**Input**
["RecentCounter", "ping", "ping", "ping", "ping"]
[[], [1], [100], [3001], [3002]]
**Output**
[null, 1, 2, 3, 3]

**Explanation**
RecentCounter recentCounter = new RecentCounter();
recentCounter.ping(1);     // requests = [1], range is [-2999,1], return 1
recentCounter.ping(100);   // requests = [1, 100], range is [-2900,100], return 2
recentCounter.ping(3001);  // requests = [1, 100, 3001], range is [1,3001], return 3
recentCounter.ping(3002);  // requests = [1, 100, 3001, 3002], range is [2,3002], return 3

# Approach
- We need to pay attention to -> `It is **guaranteed** that every call to `ping` uses a strictly larger value of `t` than the previous call.`
- The above statement is what clears how we can use a [[queue]] for this problem. 
- At every request/`ping` we add the current request time `t` to the requests and return the number of requests made in the last *3000 ms* which would give us the inclusive range of [t- 3000, t].
- When we return the number of requests made in the last *3000 ms* we need to return the count of elements that are $\geq (t-3000)$ and since it is guaranteed that every call is larger than previous call we can be sure they are sorted.
- So when we need to count the elements that satisfy the condition we can just use a [[queue]] and **pop** from the queue if it out of the range cause we won't need it again and hence we can make use of a [[queue]].

# Solution 

**Time Complexity:** $~O(N)$

**Space Complexity:** $O(1)$

```python
class RecentCounter:
	def __init__(self):
		self.reqs = deque()

	def ping(self, t: int) -> int:
		self.reqs.append(t)
		r = t - 3000
		while self.reqs and self.reqs[0] < r:
			self.reqs.popleft()
		return len(self.reqs)
```
