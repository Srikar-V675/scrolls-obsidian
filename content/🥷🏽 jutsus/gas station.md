---
aliases:
  - leetcode 134
tags:
  - dsa-problem
  - dsa
dsa-patterns:
  - "[[arrays]]"
  - greedy
difficulty: medium
companies: 
publish: true
---

**DSA-PATTERNS:** [[arrays]], greedy

**DIFFICULTY:** medium

**COMPANIES:**
- 

# Problem Description

**Leetcode Link:** [Gas Station - LeetCode](https://leetcode.com/problems/gas-station/description/)

**Solution Link:** [Gas Station - Greedy - Leetcode 134 - Python - YouTube](https://www.youtube.com/watch?v=lJwbPZGo05A&t=2s)

There are `n` gas stations along a circular route, where the amount of gas at the `ith` station is `gas[i]`.

You have a car with an unlimited gas tank and it costs `cost[i]` of gas to travel from the `ith` station to its next `(i + 1)th` station. You begin the journey with an empty tank at one of the gas stations.

Given two integer arrays `gas` and `cost`, return _the starting gas station's index if you can travel around the circuit once in the clockwise direction, otherwise return_ `-1`. If there exists a solution, it is **guaranteed** to be **unique**.

**Example 1:**

```
Input: gas = [1,2,3,4,5], cost = [3,4,5,1,2]
Output: 3
Explanation:
Start at station 3 (index 3) and fill up with 4 unit of gas. Your tank = 0 + 4 = 4
Travel to station 4. Your tank = 4 - 1 + 5 = 8
Travel to station 0. Your tank = 8 - 2 + 1 = 7
Travel to station 1. Your tank = 7 - 3 + 2 = 6
Travel to station 2. Your tank = 6 - 4 + 3 = 5
Travel to station 3. The cost is 5. Your gas is just enough to travel back to station 3.
Therefore, return 3 as the starting index.
```

**Example 2:**

```
Input: gas = [2,3,4], cost = [3,4,3]
Output: -1
Explanation:
You can't start at station 0 or 1, as there is not enough gas to travel to the next station.
Let's start at station 2 and fill up with 4 unit of gas. Your tank = 0 + 4 = 4
Travel to station 0. Your tank = 4 - 3 + 2 = 3
Travel to station 1. Your tank = 3 - 3 + 3 = 3
You cannot travel back to station 2, as it requires 4 unit of gas but you only have 3.
Therefore, you can't travel around the circuit once no matter where you start.
```

# Approach
- If the total gas available (`sum(gas)`) is less than the total cost to travel (`sum(cost)`), it's impossible to complete the circuit. Return immediately.
- The problem requires finding a continuous subarray where the cumulative gas in the tank remains positive (or becomes positive).
- This ensures that the starting point of this subarray can lead to completing the circuit.
- If there is a solution, the start of the journey must begin at the index where the cumulative tank first becomes positive after traversing through negatives.
- Since `sum(gas) >= sum(cost)`, the overall balance of gas is non-negative. Any deficit (negative balances) in the tank will eventually be balanced out by a surplus (positive balances) as we traverse through the array.
- Track the cumulative tank while iterating. Whenever the tank goes negative, reset it and consider the next index as a potential starting point. Continue until the end of the array, as there must be a valid solution if feasibility is satisfied.

# Solution 

**Time Complexity:** $O(N)$

**Space Complexity:** $O(1)$

```python
if sum(gas) < sum(cost):
	return -1

tank = 0
idx = 0
for i in range(len(gas)):
	tank += (gas[i] - cost[i])
	if tank < 0:
		tank = 0
		idx = i + 1

return idx
```