# 1. Two Sum

## Problem
Given an array of integers and a target value, find the indices of the two numbers whose sum is equal to the target.

---

## Approach 1 - Brute Force

The simplest idea is to check every possible pair of elements.

- Pick one element.
- Compare it with every other element.
- If their sum equals the target, return their indices.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - HashMap (Optimal)

Instead of checking every pair, we can store the numbers we have already visited in a HashMap.

For every element:
- Find the number required to reach the target.
- Check if that number is already present in the HashMap.
- If yes, return both indices.
- Otherwise, store the current number and its index.

This avoids unnecessary comparisons and makes the solution much faster.

Time Complexity: **O(n)**

Space Complexity: **O(n)**

---

## Example

Input

nums = [2, 7, 11, 15]

target = 9

Iteration 1:
- Current number = 2
- Complement = 7
- HashMap = {2 → 0}

Iteration 2:
- Current number = 7
- Complement = 2
- 2 is already present in the HashMap.
- Answer = [0, 1]

---

## What I Learned

- HashMap is useful for fast lookups.
- Instead of searching for a pair directly, search for the required complement.
- This problem is one of the most common HashMap interview questions.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| HashMap | O(n) | O(n) |

---

## My Notes

- Learned how to use HashMap for quick lookup.
- First time solving a problem using the complement technique.
- Need to revise HashMap methods:
  - put()
  - get()
  - containsKey()