---
description: "\U0001F7E9 Easy"
---

# 53. Maximum Subarray \(value\)

## Question

Given an integer array `nums`, find the contiguous subarray \(containing at least one number\) which has the largest sum and return its sum.

**Example:**

```text
Input: [-2,1,-3,4,-1,2,1,-5,4],
Output: 6
Explanation: [4,-1,2,1] has the largest sum = 6.
```

**Follow up:**

If you have figured out the O\(_n_\) solution, try coding another solution using the divide and conquer approach, which is more subtle.

## O\(n\) Approach

nums\[i\] &gt; nums\[i\] + cur\_sum, then count start from nums\[i\] and dump every elements before it. Otherwise, add nums\[i\]. So cur\_sum is always the max subarray from 0...i 

```python
def maxSubArray(self, nums: List[int]) -> int:
    cur = s = nums[0]
    for i in range(1, len(nums)):
        cur = max(nums[i], cur + nums[i])
        if cur > s: 
            s = cur
    return s
```

## Divide and Conquer 

TODO

