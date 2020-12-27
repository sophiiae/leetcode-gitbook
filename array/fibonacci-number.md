---
description: "\U0001F7E9 Easy"
---

# 509. Fibonacci Number

The **Fibonacci numbers**, commonly denoted `F(n)` form a sequence, called the **Fibonacci sequence**, such that each number is the sum of the two preceding ones, starting from `0` and `1`. That is,

```text
F(0) = 0,   F(1) = 1
F(N) = F(N - 1) + F(N - 2), for N > 1.
```

Given `N`, calculate `F(N)`.

## Dynamic Programming

Memoization: Store computed value in memory. 

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(n\)

## Code

```python
def fib(self, N: int) -> int:
    store = [0] * (N+1)
    for i in range(1, N+1):
        if i < 3:
            f = 1
        else:
            f = store[i-1] + store[i-2]
        store[i] = f
    return store[N]
```

