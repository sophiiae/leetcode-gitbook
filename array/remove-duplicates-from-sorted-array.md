---
description: Easy
---

# 83. Remove Duplicates from Sorted Array

## Question

Given a sorted array _nums_, remove the duplicates [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) such that each element appear only _once_ and return the new length.

Do not allocate extra space for another array, you must do this by **modifying the input array** [**in-place**](https://en.wikipedia.org/wiki/In-place_algorithm) with O\(1\) extra memory.

**Example 1:**

```text
Given nums = [1,1,2],

Your function should return length = 2, with the first two elements of nums being 1 and 2 respectively.

It doesn't matter what you leave beyond the returned length.
```

**Example 2:**

```text
Given nums = [0,0,1,1,1,2,2,3,3,4],

Your function should return length = 5, with the first five elements of nums being modified to 0, 1, 2, 3, and 4 respectively.

It doesn't matter what values are set beyond the returned length.
```

## Two Pointer Approach

Two Pointers: i for distinct element, k for searching. 

If nums\[k\] is duplicate, put in i+1\(since k goes faster than i, so k &gt; i\). Therefore, nums\[0... i\] are the distinct elements in original array. 

## Complexity 

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code 

```python
def removeDuplicates(self, nums):
    """
    :type nums: List[int]
    :rtype: int
    """
    i, k = 0, 1
    while (k < len(nums)):
        if nums[k] != nums[i]:
            nums[i+1] = nums[k]
            i += 1
        k += 1
    return i+1
```

