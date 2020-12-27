---
description: "\U0001F7E9 Easy"
---

# 268. Missing Number

## Question 

Given an array containing n distinct numbers taken from `0, 1, 2, ..., n`, find the one that is missing from the array.

**Note:** If array is sorted, then the binary search will be the optimal for searching. 

**Example 1:**

```text
Input: [3,0,1]
Output: 2
```

**Example 2:**

```text
Input: [9,6,4,2,3,5,7,0,1]
Output: 8
```

**Note**:  
Your algorithm should run in linear runtime complexity. Could you implement it using only constant extra space complexity?

## Hash Set Approach 

* Time complexity: O\(n\)
* Space complexity: O\(n\)

```python
def missingNumber(self, nums: List[int]) -> int:
    num_set = set(nums) # set() return array with distinct elements
    for num in nums: 
        if num not in num_set: 
            return num
```

## Bi Manipulation 

Because we know that `nums` contains nn numbers and that it is missing exactly one number on the range \[0..n-1\]\[0..n−1\], we know that nn definitely replaces the missing number in `nums`. Therefore, if we initialize an integer to nn and XOR it with every index and value, we will be left with the missing number. Consider the following example \(the values have been sorted for intuitive convenience, but need not be\):

| Index | 0 | 1 | 2 | 3 |
| :--- | :--- | :--- | :--- | :--- |
| Value | 0 | 1 | 3 | 4 |

$$\begin{aligned} missing &= 4 \wedge (0 \wedge 0) \wedge (1 \wedge 1) \wedge (2 \wedge 3) \wedge (3 \wedge 4) \\ &= (4 \wedge 4) \wedge (0 \wedge 0) \wedge (1 \wedge 1) \wedge (3 \wedge 3) \wedge 2 \\ &= 0 \wedge 0 \wedge 0 \wedge 0 \wedge 2 \\ &= 2 \end{aligned}$$

* Time complexity: O\(n\)
* Space complexity: O\(1\)

```python
def missingNumber(self, nums):
    missing = len(nums)
    for i, num in enumerate(nums):
        missing ^= i ^ num
    return missing
```

## Partial Sums Approach

$$1+2+3+...+n= n(n+1)/2$$

If no missing number, the sum should be $$n(n+1)/2$$. Since array only contain distinct numbers, the missing number will equal to the difference between actual sum and sum of natural numbers up to n.  

* Time complexity: O\(n\)
* Space complexity: O\(1\)

```python
def missingNumber(self, nums: List[int]) -> int:
    n = len(nums)        
    expected = (n+1)*n / 2 
    return int(expected - sum(nums))
```

