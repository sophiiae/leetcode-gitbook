---
description: Easy
---

# 414. Third Maximum Number

Given a **non-empty** array of integers, return the **third** maximum number in this array. If it does not exist, return the maximum number. The time complexity must be in O\(n\).

**Example 1:**  


```text
Input: [3, 2, 1]

Output: 1

Explanation: The third maximum is 1.
```

**Example 2:**  


```text
Input: [1, 2]

Output: 2

Explanation: The third maximum does not exist, so the maximum (2) is returned instead.
```

**Example 3:**  


```text
Input: [2, 2, 3, 1]

Output: 1

Explanation: Note that the third maximum here means the third maximum distinct number.
Both numbers with value 2 are both considered as second maximum.
```

## One Pass Approach 

first &gt; second &gt; third.  Shift the value for each in every iteration 

* Time complexity: O\(n\)
* Space complexity: O\(1\)

```python
def thirdMax(self, nums: List[int]) -> int:
    arr = [float('-inf'),float('-inf'),float('-inf')]
        
    for num in nums:
        if num not in arr:
            if num > arr[0]: arr = [num,arr[0],arr[1]]
            elif num > arr[1]: arr = [arr[0],num,arr[1]]
            elif num > arr[2]: arr = [arr[0],arr[1],num]
            
    return arr[2] if float('-inf') not in arr else max(nums)
```

## Sort Approach \(Not satisfy time complexity requirement\)

* Time complexity: O\(n log n\)
* Space complexity: O\(1\)

```python
def thirdMax(self, nums: List[int]) -> int:
    nums = [n for n in set(nums)]
    nums.sort()
    if len(nums) < 3:
        return nums[-1]
    else:
        return nums[-3]
```

