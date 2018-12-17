Title: [LeetCode 27] Remove Element
Category: Leetcode
Tags: Array, Two Pointers, Google
Date: 2018-12-16 22:45
Authors: scbai

### Question 

[link](https://leetcode.com/problems/remove-element/)

<div class="question-content">
            <p></p><p>Given an array and a value, remove all instances of that value in place and return the new length.
</p>

<p>
The order of elements can be changed. It doesn't matter what you leave beyond the new length.
</p><p></p>
</div>

### Solution

Similar to the question __[LeetCode 26] Remove Duplicates From Sorted Array__. Use 2 pointers. 

### Code

```python
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        last = 0
        for i in xrange(len(nums)):
            if nums[i] != val:
                nums[last] = nums[i]
                last += 1

        return last
```