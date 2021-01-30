# Longest Common Prefix

## Description
Write a function to find the longest common prefix string amongst an array of strings.

If there is no common prefix, return an empty string "".

Example 1:
```
Input: ["flower","flow","flight"]
Output: "fl"
```
Example 2:
```
Input: ["dog","racecar","car"]
Output: ""
Explanation: There is no common prefix among the input strings.
```
Note:

All given inputs are in lowercase letters a-z.

## My solution
- Code
```
class Solution:
    def longestCommonPrefix(self, strs):
        if len(strs)==0:
            return ""
        if len(strs)==1:
            return strs[0]
        
        res = strs[0]
        index = 1
        while index < len(strs):
            res = self.findLongest(res, strs[index])
            if res=="":
                return ""
            index += 1
        return res
        
    def findLongest(self, str1, str2):
        res = ""
        for i in range(min(len(str1), len(str2))):
            if str1[i]==str2[i]:
                res += str1[i]
            else:
                break
        return res
```
- Performance
  - Runtime: 40 ms, faster than 17.65% of Python3 online submissions for Longest Common Prefix.
  - Memory Usage: 12.8 MB, less than 100.00% of Python3 online submissions for Longest Common Prefix.

## Optimal solution
- Code
```
class Solution:
    def longestCommonPrefix(self, strs):
        minL = min(map(len, strs)) if strs else 0
        for i in range(minL):
            for j in range(1, len(strs)):
                if strs[j][i] != strs[0][i]:
                    return strs[0][:i]
        return strs[0][:minL] if minL else ""
```
- Performance
  - Runtime: 36 ms, faster than 33.38% of Python3 online submissions for Longest Common Prefix.
  - Memory Usage: 13 MB, less than 98.10% of Python3 online submissions for Longest Common Prefix.
