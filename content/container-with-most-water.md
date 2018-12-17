Title: [LeetCode 11] Container With Most Water
Category: Leetcode
Tags: Array, Two Pointers, Google
Date: 2018-12-12
Authors: scbai

### Question 

[link](https://leetcode.com/problems/container-with-most-water/)

<div class="question-content">
            <p></p><p>Given <i>n</i> non-negative integers <i>a<sub>1</sub></i>, <i>a<sub>2</sub></i>, ..., <i>a<sub>n</sub></i>, where each represents a point at coordinate (<i>i</i>, <i>a<sub>i</sub></i>). <i>n</i> vertical lines are drawn such that the two endpoints of line <i>i</i> is at (<i>i</i>, <i>a<sub>i</sub></i>) and (<i>i</i>, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.
</p>
<p>Note: You may not slant the container.
</p><p></p>
</div>

### Analysis

Assume i and j are 2 points in x-axis where i < j. The container volume is decided by the shorter height among the two. 

Assume i is lower than j, there will be no i < jj < j that makes the area of (i,jj) greater than area of (i,j). __In other words, all (i,jj) is smaller than (i,j) so there's no need to check them__. 

Thus we move i forward by 1. This idea is explained in [this post](http://jane4532.blogspot.sg/2013/05/container-with-most-water-leetcode.html). 

### Solution

__Two-pointer scan__. And always move the shorter board index (if we consider it to be a rectangle bucket), as explained in [this post](http://fisherlei.blogspot.sg/2013/01/leetcode-container-with-most-water.html).

### Code 

```python
class Solution(object):
    # @return an integer
    def maxArea(self, height):
        max_area, i, j = 0, 0, len(height) - 1
        while i < j:
            max_area = max(max_area, min(height[i], height[j]) * (j - i))
            if height[i] < height[j]:
                i += 1
            else:
                j -= 1
        return max_area
```