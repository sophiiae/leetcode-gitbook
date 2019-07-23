# Implement strStr\(\)

## Question

Implement [strStr\(\)](http://www.cplusplus.com/reference/cstring/strstr/).

Return the index of the first occurrence of needle in haystack, or **-1** if needle is not part of haystack.

**Example 1:**

```text
Input: haystack = "hello", needle = "ll"
Output: 2
```

**Example 2:**

```text
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

**Clarification:**

What should we return when `needle` is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when `needle` is an empty string. This is consistent to C's [strstr\(\)](http://www.cplusplus.com/reference/cstring/strstr/) and Java's [indexOf\(\)](https://docs.oracle.com/javase/7/docs/api/java/lang/String.html#indexOf%28java.lang.String%29).

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code 

```python
def strStr(self, haystack: str, needle: str) -> int:
    lenHaystack = len(haystack)
    lenNeedle = len(needle)
    if lenHaystack < lenNeedle:
        return -1
    elif lenNeedle == 0:
        return 0
    for i in range(lenHaystack):
        if haystack[i:i+lenNeedle] == needle:
            return i
    return -1
```

