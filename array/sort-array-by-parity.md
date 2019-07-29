# Sort Array By Parity

## Question

Given an array `A` of non-negative integers, return an array consisting of all the even elements of `A`, followed by all the odd elements of `A`.

You may return any answer array that satisfies this condition.

**Example 1:**

```text
Input: [3,1,2,4]
Output: [2,4,3,1]
The outputs [4,2,3,1], [2,4,1,3], and [4,2,1,3] would also be accepted.
```

**Note:**

1. `1 <= A.length <= 5000`
2. `0 <= A[i] <= 5000`

## Two Pointer Approach 

* Time complexity: O\(n\)
* Space complexity: O\(1\)

```python
def sortArrayByParity(A: List[int]) -> List[int]:
    i,j = 0, 0
    while j < len(A):
        if A[i] % 2 == 0: 
            i += 1
            j += 1
        elif A[j] % 2 == 0:
            A[i], A[j] = A[j], A[i]
            i += 1
        else: 
            j += 1
    return A
```

## Sort

* Time complexity: O\(n log n\)
* Space complexity: O\(n\) – depends on build-in implementation of sort

```python
def sortArrayByParity(A):
    A.sort(key = lambda x: x % 2)
    return A
```

