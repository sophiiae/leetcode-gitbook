# Longest Common Prefix

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
    strs.sort()
    for i,c in enumerate(strs[0]):
        for j in range(1, len(strs)):
            if i == len(strs[j]) or strs[j][i] != c:
                return strs[0][:i]
    return strs[0]
```



