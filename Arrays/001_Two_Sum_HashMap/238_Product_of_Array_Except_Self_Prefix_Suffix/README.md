# 238. Product of Array Except Self

## Problem

Given an integer array `nums`, return an array `answer` such that `answer[i]` is equal to the product of all the elements of `nums` except `nums[i]`.

You must solve it without using division and in **O(n)** time.

---

## Approach 1 - Brute Force

For every index:

- Calculate the product of all other elements except the current one.
- Store the product in the answer array.
- Repeat this for every index.

Time Complexity: **O(n²)**

Space Complexity: **O(1)** (excluding the output array)

---

## Approach 2 - Prefix and Suffix Product (Optimal)

Instead of multiplying all elements repeatedly, calculate the product of elements on the left and right of every index.

Steps:

- Traverse from left to right and store the product of all previous elements.
- Traverse from right to left while maintaining a suffix product.
- Multiply the left product and the right product to get the final answer.

This avoids using division and solves the problem in one forward and one backward pass.

Time Complexity: **O(n)**

Space Complexity: **O(1)** (excluding the output array)

---

## Example

Input

nums = [1, 2, 3, 4]

Left Pass:

- answer = [1, 1, 2, 6]

Right Pass:

- Index 3 → answer = [1, 1, 2, 6]
- Index 2 → answer = [1, 1, 8, 6]
- Index 1 → answer = [1, 12, 8, 6]
- Index 0 → answer = [24, 12, 8, 6]

Output

answer = [24, 12, 8, 6]

---

## What I Learned

- Prefix products store the multiplication of all elements before the current index.
- Suffix products store the multiplication of all elements after the current index.
- Combining both gives the required answer without using division.
- This is a common interview problem on arrays.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force | O(n²) | O(1) |
| Prefix & Suffix Product | O(n) | O(1)* |

\* Extra space excluding the output array.

---

## My Notes

- Learned the Prefix and Suffix Product technique.
- No division is required.
- Need to revise:
  - Prefix Product
  - Suffix Product
  - Array Traversal
  - In-place calculations