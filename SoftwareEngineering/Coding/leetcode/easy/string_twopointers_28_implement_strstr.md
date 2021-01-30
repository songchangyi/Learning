# Implement strStr()

## Description
Implement strStr().

Return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Example 1:
```
Input: haystack = "hello", needle = "ll"
Output: 2
```
Example 2:
```
Input: haystack = "aaaaa", needle = "bba"
Output: -1
```

## My solution
- Code
```
class Solution:
    def strStr(self, haystack, needle):
        if not needle:
            return 0
        if not haystack:
            return -1
        ind_h = 0
        while (len(haystack)-ind_h >= len(needle)):
            if haystack[ind_h:ind_h+len(needle)] == needle:
                return ind_h
            ind_h += 1            
        return -1
```
- Performance
  - Runtime: 28 ms, faster than 74.98% of Python3 online submissions for Implement strStr().
  - Memory Usage: 14.1 MB, less than 10.77% of Python3 online submissions for Implement strStr().

## Optimal solution
- Code
- Performance
