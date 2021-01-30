# Roman to integer

## Description
Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```
For example, two is written as II in Roman numeral, just two one's added together. Twelve is written as, XII, which is simply X + II. The number twenty seven is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

- I can be placed before V (5) and X (10) to make 4 and 9. 
- X can be placed before L (50) and C (100) to make 40 and 90. 
- C can be placed before D (500) and M (1000) to make 400 and 900.

Given a roman numeral, convert it to an integer. Input is guaranteed to be within the range from 1 to 3999.

## My solution
- Code
```
class Solution:
    def romanToInt(self, s):
        dict_ = {'I':1, 'V':5, 'X':10, 'L':50,
                 'C':100, 'D':500, 'M':1000}
        res = 0
        for i, c in enumerate(s):
            if c in ['I', 'X', 'C']:
                # end
                if (i+1) == len(s):
                    res += dict_[c]
                else:
                    # subtract
                    if dict_[c] < dict_[s[i+1]]:
                        res -= dict_[c]
                    # represent 1
                    else:
                        res += dict_[c]
            else:
                res += dict_[c]
        return res
```
- Performance
  - Runtime: 48 ms, faster than 52.38% of Python3 online submissions for Roman to Integer.
  - Memory Usage: 13 MB, less than 100.00% of Python3 online submissions for Roman to Integer.

## Optimal solution
- Code
```
class Solution:
    def romanToInt(self, s):
        d = {'M':1000, 'D':500, 'C':100, 'L':50, 'X':10, 'V':5, 'I':1}
        
        res, p = 0, 'I'
        for c in s[::-1]:
            res, p = res - d[c] if d[c] < d[p] else res + d[c], c
        return res
```
- Performance
  - Runtime: 36 ms, faster than 95.93% of Python3 online submissions for Roman to Integer.
  - Memory Usage: 12.9 MB, less than 100.00% of Python3 online submissions for Roman to Integer.
