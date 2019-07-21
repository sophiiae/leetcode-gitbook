# Two Sum

## Question

Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have _**exactly**_ one solution, and you may not use the _same_ element twice.

**Example:**

```text
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```

## **Hash Table**

Calculate the `remainder` after subtracting element from target, if the remainder can be found in the loop up table, then we can get the `index` and return the result. Otherwise, we add current element to the table. 

## Complexity 

* Time complexity: O\(n\)
* Space complexity: O\(n\)

## Code

```python
def twoSum(self, nums, target):
    """
    :type nums: List[int]
    :type target: int
    :rtype: List[int]
    """
    table = {}
    for i in range(0, len(nums)):
        remain = target - nums[i]
        if (x in table):
            return [table[remain], i]
        table[nums[i]] = i
```

