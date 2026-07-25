# 560. Subarray Sum Equals K

## Problem

Given an integer array `nums` and an integer `k`, return the total number of continuous subarrays whose sum equals `k`.

---

## Approach 1 - Brute Force

Check every possible subarray.

- Start from each index.
- Keep adding the elements one by one.
- If the sum becomes equal to `k`, increase the count.
- Repeat for every starting index.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - Prefix Sum + HashMap (Optimal)

Instead of calculating the sum of every subarray repeatedly, use Prefix Sum and a HashMap.

For every element:

- Keep adding the current element to the prefix sum.
- Check if `(prefixSum - k)` exists in the HashMap.
- If it exists, add its frequency to the answer.
- Store the current prefix sum in the HashMap.

The HashMap stores how many times each prefix sum has appeared.

Time Complexity: **O(n)**

Space Complexity: **O(n)**

---

## Example

Input

nums = [1, 1, 1]

k = 2

Initially

- Prefix Sum = 0
- HashMap = {0 : 1}
- Count = 0

Iteration 1:

- Number = 1
- Prefix Sum = 1
- Prefix Sum - k = -1
- Not found
- HashMap = {0:1, 1:1}

Iteration 2:

- Number = 1
- Prefix Sum = 2
- Prefix Sum - k = 0
- Found once
- Count = 1
- HashMap = {0:1, 1:1, 2:1}

Iteration 3:

- Number = 1
- Prefix Sum = 3
- Prefix Sum - k = 1
- Found once
- Count = 2
- HashMap = {0:1, 1:1, 2:1, 3:1}

Answer = 2

---

## What I Learned

- Prefix Sum helps calculate subarray sums efficiently.
- HashMap stores the frequency of prefix sums.
- The expression `(prefixSum - k)` helps identify previous prefix sums that form a valid subarray.
- This is one of the most important Prefix Sum interview problems.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| Prefix Sum + HashMap | O(n) | O(n) |

---

## My Notes

- Learned the Prefix Sum technique.
- Combined Prefix Sum with HashMap to optimize the solution.
- Need to revise:
  - Prefix Sum
  - HashMap
  - getOrDefault()
  - Frequency counting