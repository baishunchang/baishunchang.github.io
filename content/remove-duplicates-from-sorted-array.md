Title: [LeetCode 26] Remove Duplicates from Sorted Array
Category: Leetcode
Tags: Array, Two Pointers, Google
Date: 2018-12-16
Authors: scbai

### Question 

[link](https://leetcode.com/problems/remove-duplicates-from-sorted-array/)

<div class="question-content">
            <p></p><p>
Given a sorted array, remove the duplicates in place such that each element appear only <i>once</i> and return the new length.</p>

<p>
Do not allocate extra space for another array, you must do this in place with constant memory.
</p>

<p>
For example,<br>
Given input array A = <code>[1,1,2]</code>,
</p>
<p>
Your function should return length = <code>2</code>, and A is now <code>[1,2]</code>.
</p><p></p>
</div>

### Analysis

This question is easy. 

### Solution

Two pointer operations. A very similar question is __[LeetCode 27] Remove Element__. 

### Code 

```python
class Solution(object):
    # @param a list of integers
    # @return an integer
    def removeDuplicates(self, nums):
        if not nums:
            return 0

        last = 0
        for i in xrange(len(nums)):
            if nums[last] != nums[i]:
                last += 1
                nums[last] = nums[i]
        return last + 1
```