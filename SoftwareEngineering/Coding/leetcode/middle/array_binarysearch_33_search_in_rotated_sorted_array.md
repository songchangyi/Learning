# Search in Rotated Sorted Array

## Description
Suppose an array sorted in ascending order is rotated at some pivot unknown to you beforehand.

(i.e., [0,1,2,4,5,6,7] might become [4,5,6,7,0,1,2]).

You are given a target value to search. If found in the array return its index, otherwise return -1.

You may assume no duplicate exists in the array.

Your algorithm's runtime complexity must be in the order of O(log n).

Example 1:
```
Input: nums = [4,5,6,7,0,1,2], target = 0
Output: 4
```
Example 2:
```
Input: nums = [4,5,6,7,0,1,2], target = 3
Output: -1
```

## My solution
- Code
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        if len(nums) < 3:
            return self.inputCheck(nums, 0, len(nums)-1, target)
        return self.binarySearch(nums, 0, len(nums)-1, target)
        
    def binarySearch(self, nums, begin, end, target):
        if end - begin + 1 < 3:
            return self.inputCheck(nums, begin, end, target)
        mid = int((begin+end)/2)
        if nums[mid] == target:
            return mid
        if nums[mid] > nums[begin]:
            if target >= nums[begin] and target < nums[mid]:
                return self.binarySearch(nums, begin, mid, target)
            return self.binarySearch(nums, mid, end, target)
        if nums[mid] < nums[end]:
            if target > nums[mid] and target <= nums[end]:
                return self.binarySearch(nums, mid, end, target)
            return self.binarySearch(nums, begin, mid, target)
    
    def inputCheck(self, nums, begin, end, target):
        # len 0
        if begin > end:
            return -1
        # len 1
        if begin == end:
            if nums[begin] == target:
                return begin
            return -1
        # len 2
        if begin + 1 == end:
            if target  == nums[begin]:
                return begin
            elif target == nums[end]:
                return end
            return -1
```
- Performance
  - Runtime: 36 ms, faster than 87.50% of Python3 online submissions for Search in Rotated Sorted Array.
  - Memory Usage: 14.1 MB, less than 6.29% of Python3 online submissions for Search in Rotated Sorted Array.
  
## Optimal solution
- Code
```
class Solution:
    def search(self, nums: List[int], target: int) -> int:
        if not nums:
            return -1
        low, high = 0, len(nums)-1
        while low <= high:
            mid = (low + high) >> 1
            if nums[mid] == target:
                return mid
            if nums[mid] >= nums[low]:
                if nums[low] <= target < nums[mid]:
                    high = mid - 1
                else:
                    low = mid + 1
            if nums[mid] <= nums[high]:
                if nums[mid] < target <= nums[high]:
                    low = mid + 1
                else:
                    high = mid - 1
        return -1
```
- Performance
  - Runtime: 44 ms, faster than 25.38% of Python3 online submissions for Search in Rotated Sorted Array.
  - Memory Usage: 14.2 MB, less than 6.29% of Python3 online submissions for Search in Rotated Sorted Array.
