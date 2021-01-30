# Valid Parentheses

## Description
Given a string containing just the characters '(', ')', '{', '}', '[' and ']', determine if the input string is valid.

An input string is valid if:

    1. Open brackets must be closed by the same type of brackets.
    2. Open brackets must be closed in the correct order.

Note that an empty string is also considered valid.

Example 1:
```
Input: "()"
Output: true
```
Example 2:
```
Input: "()[]{}"
Output: true
```
Example 3:
```
Input: "(]"
Output: false
```
Example 4:
```
Input: "([)]"
Output: false
```
Example 5:
```
Input: "{[]}"
Output: true
```

## My solution
- Code
```
class Solution:
    def isValid(self, s) :
        # if empty
        if len(s) == 0:
            return True
        # if str
        dict_ = {'(':1, '[':2, '{':3,
                 ')':-1, ']':-2, '}':-3}
            # if illegal start
        if s[0] not in dict_ or dict_[s[0]] < 0:
            return False
        stack = [dict_[s[0]]]
        for _ in s[1:]:
            if dict_[_] > 0:
                stack.append(dict_[_])
            else:
                if len(stack) == 0:
                    return False
                elif dict_[_] + stack[-1] == 0:
                    stack.pop()
                else:
                    return False
        if sum(stack) == 0:
            return True
        return False
```
- Performance
    - Runtime: 32 ms, faster than 35.44% of Python3 online submissions for Valid Parentheses.
    - Memory Usage: 13 MB, less than 98.26% of Python3 online submissions for Valid Parentheses.

## Optimal solution
- Code
```
class Solution:
    def isValid(self, s) :
        if not s:
            return True
        left, right, stack = "([{", ")]}", []
        for i in s:
            if i in left:
                stack.append(i)
            elif not stack or left.find(stack[-1]) != right.find(i):
                return False
            else:
                stack.pop()
        return not stack
```
- Performance
    - Runtime: 24 ms, faster than 90.37% of Python3 online submissions for Valid Parentheses.
    - Memory Usage: 13 MB, less than 98.26% of Python3 online submissions for Valid Parentheses.
