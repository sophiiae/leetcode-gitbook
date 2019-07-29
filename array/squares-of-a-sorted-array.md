# Squares of a Sorted Array

## Question 

Given an array of integers `A` sorted in non-decreasing order, return an array of the squares of each number, also in sorted non-decreasing order.

**Examples:**

```text
Input: [-4,-1,0,3,10],     [-7,-3,2,3,11]
Output: [0,1,9,16,100],    [4,9,9,49,121]
```

**Note:**

1. `1 <= A.length <= 10000`
2. `-10000 <= A[i] <= 10000`
3. `A` is sorted in non-decreasing order.

## Two Pointer Approach

* Time complexity: O\(n\)
* Space complexity: O\(n\)

```python
def sortedSquares(self, A: List[int]) -> List[int]:
    B = [0] * len(A)
    k = len(B) - 1
    i, j = 0, len(A) - 1
    
    while (i <= j): 
        #compare squares before add to result array
        I = A[i] * A[i]
        J = A[j] * A[j]
        if I < J: 
            B[k] = J
            j -= 1
        else:
            B[k] = I
            i += 1
        k -= 1
    return B
```

## Sort

* Time complexity: O\(n log n\)
* Space complexity: O\(n\)

```python
def sortedSquares(A):
    return sorted(x*x for x in A)
```

