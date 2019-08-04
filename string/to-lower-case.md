---
description: Easy
---

# 709. To Lower Case

## Question

Implement function ToLowerCase\(\) that has a string parameter str, and returns the same string in lowercase.

**Example 1:**

```text
Input: "Hello"
Output: "hello"
```

**Example 2:**

```text
Input: "here"
Output: "here"
```

**Example 3:**

```text
Input: "LOVELY"
Output: "lovely"
```

## Code 

```python
def toLowerCase(self, str: str) -> str:
    lower = ""
    for c in str:
        lower += chr(ord(c) + 32) if ord(c) <= 90 and ord(c) >= 65 else c
    return lower
```

