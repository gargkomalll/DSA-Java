# 424. Longest Repeating Character Replacement

## Problem

Given a string `s` and an integer `k`, you can replace at most `k` characters with any uppercase English letter.

Return the length of the longest substring containing the same letter after performing at most `k` replacements.

---

## Approach - Sliding Window + Frequency Array

Maintain a sliding window and keep track of the frequency of every character.

For every window:

- Update the frequency of the current character.
- Keep track of the maximum frequency inside the window.
- If the number of replacements required becomes greater than `k`, shrink the window.
- Update the maximum valid window length.

The number of replacements required is:

```
Window Length - Maximum Frequency
```

If this value exceeds `k`, the window is invalid.

Time Complexity: **O(n)**

Space Complexity: **O(1)**

---

## Example

Input

```
s = "AABABBA"
k = 1
```

Window expands:

- A
- AA
- AAB
- AABA

Longest valid window = **4**

Output

```
4
```

---

## What I Learned

- Sliding Window can solve many substring problems efficiently.
- Instead of checking every substring, maintain a valid window.
- The key observation is:

```
Window Length - Maximum Frequency <= k
```

- A frequency array is faster than a HashMap when characters are limited to uppercase English letters.

---

## Complexity

| Approach | Time | Space |
|----------|------|-------|
| Sliding Window | O(n) | O(1) |

---

## My Notes

- Learned how to maintain character frequencies in a sliding window.
- Understood why only the most frequent character matters.
- Practiced using a frequency array for constant-time updates.