# Relative Sort Array

## Question

Given two arrays `arr1` and `arr2`, the elements of `arr2` are distinct, and all elements in `arr2` are also in `arr1`.

Sort the elements of `arr1` such that the relative ordering of items in `arr1` are the same as in `arr2`.  Elements that don't appear in `arr2` should be placed at the end of `arr1` in **ascending** order.

**Example 1:**

```text
Input: arr1 = [2,3,1,3,2,4,6,7,9,2,19], arr2 = [2,1,4,3,9,6]
Output: [2,2,2,1,4,3,3,9,6,7,19]
```

**Constraints:**

* `arr1.length, arr2.length <= 1000`
* `0 <= arr1[i], arr2[i] <= 1000`
* Each `arr2[i]` is distinct.
* Each `arr2[i]` is in `arr1`.

## Complexity 

* Time complexity: O\(n log n\)
* Space complexity: O\(arr1\)

## Code

```python
def relativeSortArray(self, arr1: List[int], arr2: List[int]) -> List[int]:
    ans, cnt = [], collections.Counter(arr1)
    for i in arr2: 
        if cnt[i]: ans.extend([i] * cnt.pop(i))
    rest = cnt.elements() # return iterator over elements repeat as its count
    ans.extend(sorted(rest))   
    return ans
```

