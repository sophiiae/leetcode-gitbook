---
description: "\U0001F7E9 Easy"
---

# 283. Move Zeroes

## Question

Given an array `nums`, write a function to move all `0`'s to the end of it while maintaining the relative order of the non-zero elements.

**Example:**

```text
Input: [0,1,0,3,12]
Output: [1,3,12,0,0]
```

**Note**:

1. You must do this **in-place** without making a copy of the array.
2. Minimize the total number of operations.

## Two Pointer Approach

One pointer for zero, one for non-zeros. Swap elements to move non-zero element forward. 

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code 

```python
def moveZeroes(self, nums: List[int]) -> None:
    """ Do not return anything, modify nums in-place instead."""
    if len(nums)==0 or not nums:
        return
    j=0
    for i in range(len(nums)):
        if nums[i]: # nums[i] != 0
            if not nums[j]: # nums[j] == 0
                nums[i], nums[j] = nums[j], nums[i] #swap
            j +=1
```

