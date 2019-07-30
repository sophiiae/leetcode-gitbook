# Height Checker

## Question

Students are asked to stand in non-decreasing order of heights for an annual photo.

Return the minimum number of students not standing in the right positions.  \(This is the number of students that must move in order for all students to be standing in non-decreasing order of height.\)

**Example 1:**

```text
Input: [1,1,4,2,1,3]
Output: 3
Explanation: 
Students with heights 4, 1 and 3 are not standing in the right positions.
```

**Note:**

1. `1 <= heights.length <= 100`
2. `1 <= heights[i] <= 100`

## Code 

```python
def heightChecker(self, heights: List[int]) -> int:
    s = sorted(heights)
    count = 0
    for i in range(len(heights)):
        if s[i] != heights[i]:
            count += 1
    return count
```

