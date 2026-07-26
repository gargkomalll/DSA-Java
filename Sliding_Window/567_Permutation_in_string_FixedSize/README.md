# 567. Permutation in String

## Problem

Given two strings `s1` and `s2`, return `true` if `s2` contains a permutation of `s1`, otherwise return `false`.

A permutation is any rearrangement of the characters of a string.

---

## Approach - Fixed Size Sliding Window + Frequency Array

Since every permutation of `s1` has the **same length**, we maintain a sliding window of size `s1.length()` over `s2`.

- Store the frequency of each character in `s1`.
- Maintain another frequency array for the current window in `s2`.
- Expand the window by moving the right pointer.
- If the window size exceeds `s1.length()`, remove the leftmost character.
- Whenever the window size becomes equal to `s1.length()`, compare both frequency arrays.
- If they are identical, a permutation exists.

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

- Learned how to use a **Fixed Size Sliding Window**.
- Understood that every permutation has the same length, so the window size never changes.
- Used two frequency arrays to compare character frequencies efficiently.
- Learned that comparing frequency arrays is easier than generating all permutations.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Fixed Size Sliding Window + Frequency Array | O(n) | O(1) |

---

## My Notes

- Pattern used: **Fixed Size Sliding Window**.
- Used two pointers (`left` and `right`) to maintain the window.
- Used two frequency arrays:
  - `s1Freq[]` stores the frequency of characters in `s1`.
  - `windowFreq[]` stores the frequency of characters in the current window of `s2`.
- `Arrays.equals()` is used to compare both frequency arrays.
- Since the arrays have a fixed size of **26**, comparing them takes constant time.