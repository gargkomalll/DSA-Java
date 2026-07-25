# 121. Best Time to Buy and Sell Stock

## Problem

You are given an integer array `prices` where `prices[i]` is the price of a stock on the `i-th` day.

You want to maximize your profit by choosing a single day to buy one stock and a different day in the future to sell that stock.

Return the maximum profit you can achieve. If no profit is possible, return `0`.

---

## Approach 1 - Brute Force

Try buying the stock on every day and selling it on every future day.

- Pick a buying day.
- Compare it with every possible selling day after it.
- Calculate the profit for each pair.
- Keep track of the maximum profit.
- If no profitable transaction exists, return `0`.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - One Pass (Optimal)

Instead of checking every pair, keep track of the lowest price seen so far.

For every price:

- Update the minimum buying price if the current price is lower.
- Calculate the profit if we sell today.
- Update the maximum profit if the current profit is greater.
- Continue until the end of the array.

This allows us to find the answer in a single traversal.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

prices = [7, 1, 5, 3, 6, 4]

Iteration 1:
- Price = 7
- Minimum Price = 7
- Maximum Profit = 0

Iteration 2:
- Price = 1
- Minimum Price = 1
- Maximum Profit = 0

Iteration 3:
- Price = 5
- Profit = 5 - 1 = 4
- Maximum Profit = 4

Iteration 4:
- Price = 3
- Profit = 3 - 1 = 2
- Maximum Profit = 4

Iteration 5:
- Price = 6
- Profit = 6 - 1 = 5
- Maximum Profit = 5

Iteration 6:
- Price = 4
- Profit = 4 - 1 = 3
- Maximum Profit = 5

Answer = 5

---

## What I Learned

- Greedy algorithms can solve optimization problems efficiently.
- Keep track of the minimum value while traversing the array.
- Compare the current profit with the maximum profit found so far.
- One traversal is enough to solve this problem.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| One Pass (Greedy) | O(n) | O(1) |

---

## My Notes

- Learned how to solve stock problems using a greedy approach.
- Always buy at the lowest price seen so far.
- Need to revise:
  - Math.min()
  - Math.max()
  - Greedy technique
  - One-pass array traversal