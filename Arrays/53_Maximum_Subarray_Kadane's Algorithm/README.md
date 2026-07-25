# 53. Maximum Subarray

## Problem

Given an integer array `nums`, find the contiguous subarray with the largest sum and return its sum.

A subarray is a continuous part of the array.

---

## Approach 1 - Brute Force

Try every possible subarray.

- Start from each index.
- Extend the subarray one element at a time.
- Calculate the sum of every subarray.
- Keep track of the maximum sum.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - Kadane's Algorithm (Optimal)

Instead of calculating the sum of every subarray, keep track of the maximum sum ending at the current position.

For every element:

- Add the current element to the current sum.
- Update the maximum sum if the current sum is greater.
- If the current sum becomes negative, reset it to `0` because a negative sum can never help future subarrays.

This allows us to find the answer in just one traversal.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]

Iteration 1:
- Current Sum = -2
- Maximum Sum = -2
- Reset Current Sum to 0

Iteration 2:
- Current Sum = 1
- Maximum Sum = 1

Iteration 3:
- Current Sum = -2
- Maximum Sum = 1
- Reset Current Sum to 0

Iteration 4:
- Current Sum = 4
- Maximum Sum = 4

Iteration 5:
- Current Sum = 3
- Maximum Sum = 4

Iteration 6:
- Current Sum = 5
- Maximum Sum = 5

Iteration 7:
- Current Sum = 6
- Maximum Sum = 6

Iteration 8:
- Current Sum = 1
- Maximum Sum = 6

Iteration 9:
- Current Sum = 5
- Maximum Sum = 6

Answer = 6

---

## What I Learned

- Kadane's Algorithm finds the maximum subarray sum in one pass.
- A negative running sum is never useful for future subarrays.
- Keep updating the answer while traversing the array.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| Kadane's Algorithm | O(n) | O(1) |

---

## My Notes

- Learned Kadane's Algorithm.
- Reset the current sum whenever it becomes negative.
- Need to revise:
  - Math.max()
  - Running Sum
  - Kadane's Algorithm