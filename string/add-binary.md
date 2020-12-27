---
description: "\U0001F7E9 Easy"
---

# 67. Add Binary

## Question

Given two binary strings, return their sum \(also a binary string\).

The input strings are both **non-empty** and contains only characters `1` or `0`.

**Example 1:**

```text
Input: a = "11", b = "1"
Output: "100"
```

**Example 2:**

```text
Input: a = "1010", b = "1011"
Output: "10101"
```

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code

```python
def addBinary(self, a: str, b: str) -> str:
    # expand two string to same length
    a = "0" * (len(b) - len(a)) + a 
    b = "0" * (len(a) - len(b)) + b
    
    result, carry = "", 0
    for i in range(len(a) - 1, -1, -1):
        ans = int(a[i]) + int(b[i]) + carry
        carry = ans // 2 #floor division
        ans %= 2
        result = str(ans) + result
    if carry:
        result = "1" + result 
    return result
```

