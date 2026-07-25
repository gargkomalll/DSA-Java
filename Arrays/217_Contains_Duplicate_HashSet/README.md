# 217. Contains Duplicate

## Problem

Given an integer array `nums`, return `true` if any value appears at least twice in the array. Otherwise, return `false`.

---

## Approach 1 - Brute Force

Compare every element with every other element.

- Pick one element.
- Compare it with all remaining elements.
- If two elements are the same, return `true`.
- If no duplicate is found after checking all pairs, return `false`.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - HashSet (Optimal)

Use a HashSet to keep track of the elements we have already seen.

For every element:

- Check if it is already present in the HashSet.
- If yes, a duplicate exists, so return `true`.
- Otherwise, add the element to the HashSet.
- If the entire array is traversed without finding any duplicate, return `false`.

This avoids checking every pair of elements and makes the solution much faster.

Time Complexity: **O(n)**

Space Complexity: **O(n)**

---

## Example

Input

nums = [1, 2, 3, 1]

Iteration 1:
- Current number = 1
- HashSet = {1}

Iteration 2:
- Current number = 2
- HashSet = {1, 2}

Iteration 3:
- Current number = 3
- HashSet = {1, 2, 3}

Iteration 4:
- Current number = 1
- 1 is already present in the HashSet.
- Return true.

---

## What I Learned

- HashSet stores only unique elements.
- It provides fast lookup in average **O(1)** time.
- This problem is one of the most common HashSet interview questions.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| HashSet | O(n) | O(n) |

---

## My Notes

- Learned how to use HashSet for checking duplicates.
- Instead of comparing every pair, store visited elements.
- Need to revise HashSet methods:
  - add()
  - contains()