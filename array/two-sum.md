---
description: Easy
---

# 1. Two Sum

## Question

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have _**exactly**_ one solution, and you may not use the _same_ element twice.

**Example:**

```text
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

## **Solution 1: Hash Table**

Calculate the `remainder` after subtracting element from target, if the remainder can be found in the loop up table, then we can get the `index` and return the result. Otherwise, we add the current element to the table. 

* Time complexity: O\(n\)
* Space complexity: O\(n\)

```python
def twoSum(self, nums, target):
    table = {}
    for i in range(0, len(nums)):
        remain = target - nums[i]
        if (x in table):
            return [table[remain], i]
        table[nums[i]] = i
```

## **Solution 2: Two Pointers**

Sort the input array in non-descending order, then use two pointers, one at the first element and one at the last. If the sum of two pointed elements is greater than the target value, move the right pointer to its left. Similarly, if the sum is less, move the left pointer to its right.

* Time complexity: O\(n log n\)
* Space complexity: O\(1\)

```python
def twoSum(self, nums, target):
    nums.sort()
    left, right = 1, len(nums) - 1
    while(left < right):
        sum = nums[left] + nums[right]
        if sum == target:
            return [nums[left], nums[right]]
        elif sum > target:
            right -= 1
        else:
            left += 1
```

