---
aliases: leetcode 121
tags:
  - dsa-problem
  - dsa
dsa-patterns: 
- "[[arrays]]"
difficulty: easy
companies: 
- Google
- Amazon
publish: true
---

**DSA-PATTERNS:** [[arrays]]
**DIFFICULTY:** easy
**COMPANIES:** 
- Google
- Amazon

# Problem Definition

**Leetcode Link:** [Buy & Sell Stock](https://leetcode.com/problems/best-time-to-buy-and-sell-stock/description/)

You are given an array prices where prices[i] is the price of a given stock on the ith day.

You want to maximize your profit by choosing a single day to buy one stock and choosing a different day in the future to sell that stock.

Return the maximum profit you can achieve from this transaction. If you cannot achieve any profit, return 0.

 

Example 1:
```
Input: prices = [7,1,5,3,6,4]
Output: 5
Explanation: Buy on day 2 (price = 1) and sell on day 5 (price = 6), profit = 6-1 = 5.
Note that buying on day 2 and selling on day 1 is not allowed because you must buy before you sell.
```

Example 2:
```
Input: prices = [7,6,4,3,1]
Output: 0
Explanation: In this case, no transactions are done and the max profit = 0.
```

# Approach

It is a simple logic where you need to minimize the buy and maximize the profit, such that you buy before you sell.

We can use the `Kadane's Algo`. We can find the min buy by going from left to right and at the same time when you have the current min at hand calculate the profit you can gain from the elements. This will ensure that we are buying before selling even if the current element is teh minimum it will just end up with profit 0 and 0 can't be max. 

> **Note:**
> Try to use `if and else if` for this problem not `max and min` because max and min are slower operations.


# Solution

**Time Complexity:** O(N)
**Space Complexity:** O(1)

```python
buy = prices[0]
maxProfit = 0
for price in prices[1: ]:
    if price < buy:
        buy = price
    elif price - buy > maxProfit:
        maxProfit = price - buy
return maxProfit
```