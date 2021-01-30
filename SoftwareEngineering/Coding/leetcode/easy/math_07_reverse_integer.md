# Reverse integer

## Description
Given a 32-bit signed integer, reverse digits of an integer.

Example 1:

- Input: 123
- Output: 321

Example 2:

- Input: -123
- Output: -321

Example 3:

- Input: 120
- Output: 21

Note:
Assume we are dealing with an environment which could only store integers within the 32-bit signed integer range: [−231,  231 − 1]. 

For the purpose of this problem, assume that your function returns 0 when the reversed integer overflows.

## My solution
- code
```
import math

class Solution:
    def reverse(self, x):
        if (x <= -math.pow(2, 31)) or (x >= math.pow(2, 31)-1):
            return 0
        digits = []
        temp = x
        if x < 0:
            temp = -x
        while temp >= 10:
            digits.append(temp % 10)
            temp = int(temp / 10)
        digits.append(temp)
        ## construct new number
        res = 0
        for d in digits:
            res = res * 10 + d
        ## if negatif
        if x < 0:
            res = -res
        ## if out of scope
        if (res <= -math.pow(2, 31)) or (res >= math.pow(2, 31)-1):
            return 0
        return res
```

- Performance
  - Runtime: 32 ms, faster than 49.13% of Python3 online submissions for Reverse Integer.
  - Memory Usage: 12.8 MB, less than 100.00% of Python3 online submissions for Reverse Integer.
  
## Optimal solution
- Code
```
class Solution:
  def reverse(self, x: int) -> int:
      x = str(x)
      if (int(x)<0):
          x = int(x[0]+x[1:][::-1])
      else:
          x =int(x[::-1])
      return  x if -2147483648 <= x <= 2147483647 else 0 
```
  
- Performance
  - Runtime: 28 ms, faster than 77.33% of Python3 online submissions for Reverse Integer.
  - Memory Usage: 12.9 MB, less than 100.00% of Python3 online submissions for Reverse Integer.
