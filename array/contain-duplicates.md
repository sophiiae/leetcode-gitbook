# Contain Duplicates

## Question

Given an array of integers, find if the array contains any duplicates.

Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct.

**Example 1:**

```text
Input: [1,2,3,1]
Output: true
```

**Example 2:**

```text
Input: [1,2,3,4]
Output: false
```

**Example 3:**

```text
Input: [1,1,1,3,3,4,3,2,4,2]
Output: true
```

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(n\)

## Code 

```python
def containsDuplicate(self, nums: List[int]) -> bool:
    map = {} 
    for num in nums: 
        if map.get(num):
            return True
        map[num] = 1
    return False
```

```python
def containsDuplicate(self, nums: List[int]) -> bool:
    return len(set(nums)) < len(nums)
```

