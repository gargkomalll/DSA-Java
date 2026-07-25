# 42. Trapping Rain Water

## Problem

Given an array `height` where each element represents the height of a bar, calculate how much rainwater can be trapped after raining.

Return the total amount of trapped water.

---

## Approach 1 - Brute Force

For every bar:

- Find the tallest bar on its left.
- Find the tallest bar on its right.
- The water trapped at the current index is:
  - Minimum of left maximum and right maximum.
  - Subtract the current bar height.
- Add the trapped water for every index.

Time Complexity: **O(n²)**

Space Complexity: **O(1)**

---

## Approach 2 - Two Pointers (Optimal)

Use two pointers starting from both ends of the array.

- Maintain the highest bar seen from the left (`leftMax`).
- Maintain the highest bar seen from the right (`rightMax`).
- Compare the heights at both pointers.
- Move the pointer with the smaller height.
- If the current height is smaller than its maximum, add the trapped water.
- Otherwise, update the corresponding maximum height.

This allows us to calculate the trapped water in a single traversal.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

height = [4, 2, 0, 3, 2, 5]

Initially

- Left = 0
- Right = 5
- Left Max = 0
- Right Max = 0
- Water = 0

Iteration 1:

- Left Height < Right Height
- Left Max = 4

Iteration 2:

- Height = 2
- Water += 4 - 2 = 2

Iteration 3:

- Height = 0
- Water += 4 - 0 = 4

Iteration 4:

- Height = 3
- Water += 4 - 3 = 1

Continue until both pointers meet.

Output

9

---

## What I Learned

- Two Pointers can solve this problem without using extra arrays.
- Keep track of the maximum height from both ends.
- Water trapped depends on the smaller boundary.
- This is one of the most important Two Pointer interview problems.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| Two Pointers | O(n) | O(1) |

---

## My Notes

- Learned the Two Pointer technique.
- Maintain `leftMax` and `rightMax`.
- Move the pointer with the smaller height.
- Need to revise:
  - Two Pointers
  - Left Maximum
  - Right Maximum
  - Water Trapping Logic