# Contains Duplicate II

## Question

Given an array of integers and an integer k, find out whether there are two distinct indices i and j in the array such that `nums[i] = nums[j]` and the **absolute** difference between `i` and `j` is at most `k`.

**Example 1:**

```text
Input: nums = [1,2,3,1], k = 3
Output: true
```

**Example 2:**

```text
Input: nums = [1,0,1,1], k = 1
Output: true
```

**Example 3:**

```text
Input: nums = [1,2,3,1,2,3], k = 2
Output: false
```

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(n\)

## Code 

```python
def containsNearbyDuplicate(self, nums: List[int], k: int) -> bool:
    table = dict()
    for i,num in enumerate(nums):
        if num in table and abs(i - table[num]) <= k: 
            return True
        table[num] = i
    return False
```

