# Two sum

## Description
Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9, return [0, 1].

## My solution
- Code
```
class Solution:
    def twoSum(self, nums, target):
        length = len(nums)
        for i in range(length-1):
            for j in range(i+1, length):
                if (nums[i] + nums[j]) == target:
                    return [i, j]
        return []
```
- Performance
  - Runtime: 5820 ms, faster than 16.05% of Python3 online submissions for Two Sum.
  - Memory Usage: 14.1 MB, less than 63.49% of Python3 online submissions for Two Sum.

## Optimal solution
- Code
```
class Solution:
    def twoSum(self, nums, target):
        d = {}
        for i, num in enumerate(nums):
            if target - num in d:
                return [d[target-num], i]
            d[num] = i
```
- Performance
  - Runtime: 48 ms, faster than 78.31% of Python3 online submissions for Two Sum.
  - Memory Usage: 14.2 MB, less than 60.00% of Python3 online submissions for Two Sum.
