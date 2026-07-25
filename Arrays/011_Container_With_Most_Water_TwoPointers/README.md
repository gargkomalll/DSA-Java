# 11. Container With Most Water

## Problem

You are given an integer array `height` where each element represents the height of a vertical line.

Find two lines that together with the x-axis form a container, such that the container holds the maximum amount of water.

Return the maximum amount of water the container can store.

---

## Approach 1 - Brute Force

Check every possible pair of lines.

- Pick the first line.
- Pair it with every other line.
- Calculate the area using:
  - Width = distance between the two lines.
  - Height = minimum of the two heights.
- Keep track of the maximum area.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - Two Pointers (Optimal)

Use two pointers.

- Place one pointer at the beginning and the other at the end.
- Calculate the current area.
- Update the maximum area.
- Move the pointer having the smaller height because it limits the container.
- Continue until both pointers meet.

This reduces unnecessary comparisons and finds the maximum area efficiently.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

height = [1,8,6,2,5,4,8,3,7]

Initially

- Left = 0
- Right = 8
- Area = 8 × min(1,7) = 8
- Maximum Area = 8

Move Left Pointer

- Left = 1
- Right = 8
- Area = 7 × min(8,7) = 49
- Maximum Area = 49

Continue moving pointers until they meet.

Output

49

---

## What I Learned

- Two Pointers can optimize problems involving two ends of an array.
- Always move the pointer with the smaller height because it limits the area.
- Checking every pair is unnecessary.
- This is one of the most common Two Pointer interview problems.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| Two Pointers | O(n) | O(1) |

---

## My Notes

- Learned the Two Pointer technique.
- Move the pointer with the smaller height.
- Calculate area using:
  - Width = Right - Left
  - Height = Minimum of both heights
- Need to revise:
  - Two Pointers
  - Math.min()
  - Math.max()