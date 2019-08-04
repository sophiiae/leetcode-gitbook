---
description: Easy
---

# 169. Majority Element

## Question

Given an array of size n, find the majority element. The majority element is the element that appears **more than** `⌊ n/2 ⌋` times.

You may assume that the array is non-empty and the majority element always exist in the array.

**Example 1:**

```text
Input: [3,2,3]
Output: 3
```

**Example 2:**

```text
Input: [2,2,1,1,1,2,2]
Output: 2
```

## Boyer Moore Voting Algorithm 

\([https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore\_majority\_vote\_algorithm](https://en.wikipedia.org/wiki/Boyer%E2%80%93Moore_majority_vote_algorithm)\)

An algorithm for finding **majority** of a sequence of elements. 

**Note:** count\(majority\) &gt; count\(all non-majority\)

However, if there is no majority, the algorithm will not detect that fact. We need to make a second pass through the data to verify if the element found in the first pass really is a majority. 

## Complexity 

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code 

```python
def majorityElement(self, nums: List[int]) -> int:
    count = 0 
    n = None 
    
    for num in nums: 
        if count == 0: 
            n = num
        count += (1 if num == n else -1)
    return n
```

