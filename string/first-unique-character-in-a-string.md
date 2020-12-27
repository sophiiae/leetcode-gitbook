---
description: "\U0001F7E9 Easy"
---

# 387. First Unique Character in a String

## Question

Given a string, find the first non-repeating character in it and return it's index. If it doesn't exist, return -1.

**Examples:**

```text
s = "leetcode"
return 0.

s = "loveleetcode",
return 2.
```

**Note:** You may assume the string contain only lowercase letters.

## Code 

```python
from collections import Counter
def firstUniqChar(self, s: str) -> int:
    for k, v in Counter(s).items(): 
    # items() return the list with all dictionary keys with values
        if v == 1:
            return s.index(k)
    return -1
```

## Python Counter Object

```python
cnt = Counter()
for word in ['red', 'blue', 'red', 'green', 'blue', 'blue']:
    cnt[word] += 1
>>> Counter({'blue': 3, 'red': 2, 'green': 1})
```

