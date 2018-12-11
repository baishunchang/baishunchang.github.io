Title: [LeetCode 1] Two Sum
Category: Leetcode
Tags: Array, Hash Table, Google
Date: 2018-12-09
Authors: scbai

### Question

[link](https://leetcode.com/problems/two-sum/)

<div class="question-content">
    <p></p><p>Given an array of integers, find two numbers such that they add up to a specific target number.</p>
    <p>The function twoSum should return indices of the two numbers such that they add up to the target, where index1 must be less than index2.</p>
    <p>You may assume that each input would have exactly one solution.</p>
    <p style="font-family:monospace">
    <b>Input:</b> numbers = {2, 7, 11, 15}, target = 9<br>
    <b>Output:</b> index1 = 0, index2 = 1
    </p>
    <p></p>
</div>

### Analysis

It's __not a good idea to sort the input__, because we are supposed to return the position index. Without sorting, we must use some data structure to help us!

And the answer is HashMap. 

### Solution

Read thru the list of integers, and each time add (targer - curInt) to the hashmap. 

If the number is contained in the HashMap, solution found. 

### Code 

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        lookup = {}
        for i, num in enumerate(nums):
            if target - num in lookup:
                return [lookup[target - num], i]
            lookup[num] = i
```