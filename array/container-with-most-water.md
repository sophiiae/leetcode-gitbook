# Container With Most Water

## Question

Given n non-negative integers a1, a2, ..., an , where each represents a point at coordinate \(i, ai\). n vertical lines are drawn such that the two endpoints of line i is at \(i, ai\) and \(i, 0\). Find two lines, which together with x-axis forms a container, such that the container contains the most water.

**Note:** You may not slant the container and n is at least 2.

![](https://s3-lc-upload.s3.amazonaws.com/uploads/2018/07/17/question_11.jpg)

The above vertical lines are represented by array \[1,8,6,2,5,4,8,3,7\]. In this case, the max area of water \(blue section\) the container can contain is 49.

**Example:**

```text
Input: [1,8,6,2,5,4,8,3,7]
Output: 49
```

## Two Pointer Approach

The height of volume depends on the lower vertical line, therefore, we keep the higher one, and move the lower either forward or backward. 

What if two lines have same height? Move either one doesn't affect change the answer. 

我们假设 1 号 和 8 号 柱子高度是相等的。如果他们之间的柱子只有 1 根比它俩高或者没有比它俩高的，那么最大面积就一定选取是 1 号和 8 号了，所以 1 号接着变大，或者 8 号接着减小都是无所谓的，因为答案已经确定了。

## Complexity

* Time complexity: O\(n\)
* Space complexity: O\(1\)

## Code

```python
def maxArea(self, height: List[int]) -> int:
    most = 0
    l, r = 0, len(height) - 1
    
    while l < r:
        left, right = height[l], height[r]
        if left < right:
            currArea = (r - l) * left
            # keep going until find the one is higher, 
            # save calculation for every vertical line
            while height[l] <= left:
                l += 1
        else:
            currArea = (r - l) * right
            while height[r] <= right and r:
                r -= 1
        most = max(most, currArea)        
    return most
```

