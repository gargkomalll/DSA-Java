# 567. Permutation in String

## Problem

Given two strings `s1` and `s2`, return `true` if `s2` contains a permutation of `s1`, otherwise return `false`.

A permutation is any rearrangement of the characters of a string.

---

## Approach 1 - Brute Force

Generate all possible permutations of `s1` and check whether any permutation exists as a substring of `s2`.

Steps:

- Generate every permutation of `s1`.
- For each permutation, search whether it exists in `s2`.
- If any permutation is found, return `true`.
- Otherwise, return `false`.

Time Complexity: **O(m! × (n - m + 1) × m)**

Space Complexity: **O(m)** (for recursion stack)

> **Why not use this?**
>
> Generating all permutations becomes extremely expensive even for moderate string lengths. This approach exceeds time limits for larger inputs.

---

## Approach 2 - Fixed Size Sliding Window + Frequency Array (Optimal)

Since every permutation of `s1` has the same length, maintain a sliding window of size `s1.length()` over `s2`.

- Store the frequency of each character in `s1`.
- Maintain another frequency array for the current window in `s2`.
- Expand the window by moving the right pointer.
- If the window size exceeds `s1.length()`, remove the leftmost character.
- Whenever the window size becomes equal to `s1.length()`, compare both frequency arrays.
- If both arrays are identical, a permutation exists.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

```
s1 = "ab"
s2 = "eidbaooo"
```

Sliding Window

```
ei ❌
id ❌
db ❌
ba ✅
```

Frequency of `s1`

```
a = 1
b = 1
```

Frequency of Window `"ba"`

```
a = 1
b = 1
```

Both frequency arrays match.

Output

```
true
```

---

## What I Learned

- Learned the difference between **Fixed Size** and **Variable Size** Sliding Window.
- Understood why generating all permutations is impractical.
- Learned to compare character frequencies instead of generating permutations.
- Practiced using two frequency arrays for efficient matching.
- Used `Arrays.equals()` to compare two frequency arrays.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Brute Force (Generate All Permutations) | O(m! × (n - m + 1) × m) | O(m) |
| Fixed Size Sliding Window + Frequency Array | O(n) | O(1) |

---

## My Notes

- Pattern Used: **Fixed Size Sliding Window**
- Window size always remains equal to `s1.length()`.
- Used two pointers (`left` and `right`) to slide the window.
- Used two frequency arrays:
  - `s1Freq[]` stores frequencies of characters in `s1`.
  - `windowFreq[]` stores frequencies of characters in the current window.
- Compared both arrays using `Arrays.equals()`.
- Since the arrays have a fixed size of **26**, comparing them takes constant time.