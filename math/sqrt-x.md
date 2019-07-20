# Sqrt\(x\)

## Question

Implement `int sqrt(int x)`.

Compute and return the square root of _x_, where _x_ is guaranteed to be a non-negative integer.

Since the return type is an integer, the decimal digits are truncated and only the integer part of the result is returned.

**Example 1:**

```text
Input: 4
Output: 2
```

**Example 2:**

```text
Input: 8
Output: 2
Explanation: The square root of 8 is 2.82842..., and since 
             the decimal part is truncated, 2 is returned.
```

## Approach 1: Newton-Raphson Method

\([https://en.wikipedia.org/wiki/Newton%27s\_method\#Square\_root\_of\_a\_number](https://en.wikipedia.org/wiki/Newton%27s_method#Square_root_of_a_number)\)

**Find** $$\sqrt [ m ]{ a }$$**:** 

Set $$x^m - a = 0 $$,  $$x =\sqrt [ m ]{ a }$$

$$x_0=a$$, $$x_{ n+1 }=n_{ n }-\frac { f(x _ m)}{ f'(x_n) }$$

```python
def mySqrt(self, x: int) -> int:
    if x == 0:
        return 0
    x0 = x
    error = float('inf')
    while (error >= 1):
        # use Newton's method
        x1 = x0 - (x0 * x0 - x) / (2 * x0)
        x0 = x1
        error = abs(x0 * x0 - x)
    return int(x0)
```

## Approach 2: Binary Search

```python
def mySqrt(x):
    l = 1
    r = x
    while (l <= r):
        m = (r + l ) // 2
        if m * m > x: 
            r = m - 1
        else:
            l = m + 1
    return r
```

