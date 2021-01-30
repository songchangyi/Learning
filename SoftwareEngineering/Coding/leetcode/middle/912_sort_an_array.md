# Sort an Array

## Description
Given an array of integers nums, sort the array in ascending order.

Example 1:
```
Input: nums = [5,2,3,1]
Output: [1,2,3,5]
```
Example 2:
```
Input: nums = [5,1,1,2,0,0]
Output: [0,0,1,1,2,5]
```

## My solution [Bug free]
- Code
```
class Solution:
    def sortArray(self, nums: List[int]) -> List[int]:
        if len(nums) < 2:
            return nums
        v = nums[0]
        left, right = [], []
        for i in nums[1:]:
            if i <= v:
                left.append(i)
            else:
                right.append(i)
        return self.sortArray(left) + [v] + self.sortArray(right)
```
- Performance
  - Runtime: 260 ms, faster than 77.28% of Python3 online submissions for Sort an Array.
  - Memory Usage: 20.7 MB, less than 7.14% of Python3 online submissions for Sort an Array.
  
## Clean solution
- Code
```
class Solution:
    def sortArray(self, nums: List[int]) -> List[int]:
        if len(nums) < 2:
            return nums
        pivot = random.choice(nums)
        left  = [i for i in nums if i < pivot]
        eq    = [i for i in nums if i == pivot]
        right = [i for i in nums if i > pivot]
        return self.sortArray(left) + eq + self.sortArray(right)
```
- Performance
  - Runtime: 312 ms, faster than 52.24% of Python3 online submissions for Sort an Array.
  - Memory Usage: 20.7 MB, less than 7.14% of Python3 online submissions for Sort an Array.
  
## Optimal solution
- Code
```
def sortArray(self, nums: List[int]) -> List[int]:
        self.quicksort(nums, 0, len(nums)-1)
        return nums
    
    def partition(self, alist, left, right):
        pivot = alist[right]
        start = left
        end = right - 1
        while start <= end:
            if alist[start] < pivot:
                start += 1
            elif alist[end] >= pivot:
                end -= 1
            else:
                alist[start], alist[end] = alist[end], alist[start]
                start += 1
                end -= 1
        alist[start], alist[right] = alist[right], alist[start]
        return start
    
    def quicksort(self, alist, left, right):
        if left >= right:
            return
        pivot = self.partition(alist, left, right)
        self.quicksort(alist, left, pivot-1)
        self.quicksort(alist, pivot+1, right)
```
- Performance
  - Runtime: 268 ms, faster than 74.96% of Python3 online submissions for Sort an Array.
  - Memory Usage: 18.8 MB, less than 100.00% of Python3 online submissions for Sort an Array.
