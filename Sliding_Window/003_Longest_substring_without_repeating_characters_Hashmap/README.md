# 3. Longest Substring Without Repeating Characters

## Problem

Given a string `s`, find the length of the **longest substring** without repeating characters.

A substring is a contiguous sequence of characters.

---

## Approach 1 - Brute Force

The straightforward approach is to generate every possible substring and check whether it contains duplicate characters.

- Start from every index.
- Keep adding characters to the current substring.
- Use a HashSet to check if a character is already present.
- If a duplicate is found, stop expanding that substring.
- Keep track of the maximum length found.

Time Complexity: **O(n²)**

Space Complexity: **O(k)**

where `k` is the number of unique characters.

---

## Approach 2 - Sliding Window + HashSet (Optimal)

Instead of checking every substring repeatedly, maintain a sliding window that always contains unique characters.

For every character:

- Expand the window by moving the right pointer.
- If the current character already exists in the window:
  - Remove characters from the left until the duplicate is removed.
- Insert the current character into the HashSet.
- Update the maximum window size.

This way, every character is processed at most twice.

Time Complexity: **O(n)**

Space Complexity: **O(k)**

---

## Example

Input

s = "abcabcbb"

Iteration 1:
- Window = "a"
- Max Length = 1

Iteration 2:
- Window = "ab"
- Max Length = 2

Iteration 3:
- Window = "abc"
- Max Length = 3

Iteration 4:
- Next character = 'a'
- Duplicate found.
- Remove characters from the left until 'a' is removed.
- Window becomes "bca"

Continue the same process.

Final Answer = **3**

---

## What I Learned

- Sliding Window is useful for solving substring problems efficiently.
- HashSet helps in checking duplicate characters in constant time.
- Instead of restarting whenever a duplicate is found, simply shrink the window.
- Every character enters and leaves the window at most once, giving an **O(n)** solution.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(k) |
| Sliding Window + HashSet | O(n) | O(k) |

---

## My Notes

- Learned the Sliding Window technique for substring problems.
- Understood when to expand and when to shrink the window.
- Practiced using HashSet methods:
  - add()
  - remove()
  - contains()
- Important point: This problem deals with **substring**, so the characters must be contiguous.