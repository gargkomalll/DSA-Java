# 15. 3Sum

## Problem

Given an integer array `nums`, return all the unique triplets `[nums[i], nums[j], nums[k]]` such that:

- `i != j`
- `i != k`
- `j != k`
- `nums[i] + nums[j] + nums[k] == 0`

The solution set must not contain duplicate triplets.

---

## Approach 1 - Brute Force

Check every possible triplet.

- Pick the first element.
- Pick the second element after it.
- Pick the third element after the second.
- If their sum is `0`, store the triplet.
- Make sure duplicate triplets are not added.

Time Complexity: **O(n³)**

Space Complexity: **O(1)** (excluding the output list)

---

## Approach 2 - Sorting + Two Pointers (Optimal)

First sort the array.

For every element:

- Fix the current element as the first number.
- Use two pointers:
  - `left` starts from the next index.
  - `right` starts from the end of the array.
- Calculate the sum of the three numbers.
- If the sum is `0`, store the triplet.
- Skip duplicate values for both the fixed element and the two pointers.
- If the sum is less than `0`, move the left pointer.
- If the sum is greater than `0`, move the right pointer.

Sorting helps us avoid duplicate triplets and efficiently search using two pointers.

Time Complexity: **O(n²)**

Space Complexity: **O(1)** (excluding the output list)

---

## Example

Input

nums = [-1, 0, 1, 2, -1, -4]

After Sorting

nums = [-4, -1, -1, 0, 1, 2]

Iteration 1:

- Fixed = -4
- No valid triplet found.

Iteration 2:

- Fixed = -1
- Left = -1
- Right = 2
- Sum = 0
- Triplet = [-1, -1, 2]

Continue searching...

- Left = 0
- Right = 1
- Sum = 0
- Triplet = [-1, 0, 1]

Skip duplicate values.

Output

[[-1, -1, 2], [-1, 0, 1]]

---

## What I Learned

- Sorting simplifies many array problems.
- Two Pointers reduce the time complexity from **O(n³)** to **O(n²)**.
- Skipping duplicate values is important to avoid repeated triplets.
- This is one of the most common Two Pointer interview problems.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n³) | O(1) |
| Sorting + Two Pointers | O(n²) | O(1) |

---

## My Notes

- Learned the Sorting + Two Pointers technique.
- Always sort the array before applying two pointers.
- Skip duplicate elements for both the fixed index and pointers.
- Need to revise:
  - Arrays.sort()
  - Two Pointers
  - Duplicate Handling