---
description: "\U0001F7E9 Easy"
---

# 14. Longest Common Prefix

## Question

Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string `""`.

**Example 1:**

```text
Input: ["flower","flow","flight"]
Output: "fl"
```

**Example 2:**

```text
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```

**Note:**

All given inputs are in lowercase letters `a-z`.

## Horizontal Scanning

* Time complexity: O\(S\) – sum of all chars
* Space complexity: O\(1\)

```python
def longestCommonPrefix(self, strs: List[str]) -> str:
    if len(strs) == 0:
        return ""
    strs.sort()    # group similar words
    prefix = strs[0]
    for i in range(1, len(strs)):
        if len(prefix) == 0:
            return ""
        while(strs[i].find(prefix) != 0):
            prefix = prefix[:-1]
    return prefix
```

## Vertical Scanning

* Time complexity: O\(S\)
* Space complexity: O\(1\)

```python
def longestCommonPrefix(self, strs: List[str]) -> str:
    if len(strs) == 0:
        return ""
    i, j = 0, 0
    first = strs[0]
    while (i < len(first)):
        c = first[i] #current character
        for j, s in enumerate(strs):
            # if other string has no char or different char at i
            if i > len(s)-1 or s[i] != c:
                return first[:i]
        i += 1
    return first
```



