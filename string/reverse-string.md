---
description: "\U0001F7E9 Easy"
---

# 344. Reverse String

## Question

Write a function that reverses a string. The input string is given as an array of characters `char[]`.

Do not allocate extra space for another array, you must do this by **modifying the input array** [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) with O\(1\) extra memory.

You may assume all the characters consist of [printable ascii characters](https://en.wikipedia.org/wiki/ASCII#Printable_characters).

**Example 1:**

```text
Input: ["h","e","l","l","o"]
Output: ["o","l","l","e","h"]
```

**Example 2:**

```text
Input: ["H","a","n","n","a","h"]
Output: ["h","a","n","n","a","H"]
```

## Code

```python
def reverseString(self, s: List[str]) -> None:
    i, j = 0, len(s)-1    # Two pointers
    
    while(i<j):
        s[i],s[j] = s[j],s[i]
        i += 1
        j -= 1
```



