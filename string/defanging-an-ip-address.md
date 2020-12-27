---
description: "\U0001F7E9 Easy"
---

# 1108. Defanging an IP Address

## Question

Given a valid \(IPv4\) IP `address`, return a defanged version of that IP address.

A _defanged IP address_ replaces every period `"."` with `"[.]"`.

**Example 1:**

```text
Input: address = "1.1.1.1"
Output: "1[.]1[.]1[.]1"
```

**Example 2:**

```text
Input: address = "255.100.50.0"
Output: "255[.]100[.]50[.]0"
```

**Constraints:**

* The given `address` is a valid IPv4 address.

## Code

```python
def defangIPaddr(self, address: str) -> str:
    return address.replace(".","[.]")
```

```python
def defangIPaddr(self, address: str) -> str:
    defang = ""
    for i,c in enumerate(address):
        defang += '[.]' if c == '.' else c
    return defang
```

