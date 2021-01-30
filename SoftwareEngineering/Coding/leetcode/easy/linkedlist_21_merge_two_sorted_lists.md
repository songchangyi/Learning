# Merge Two Sorted Lists

## Description
Merge two sorted linked lists and return it as a new list. The new list should be made by splicing together the nodes of the first two lists.

Example:
```
Input: 1->2->4, 1->3->4
Output: 1->1->2->3->4->4
```

## Optimal solution
- Code
```
class Solution:
    def mergeTwoLists(self, a, b):
        if a and b:
            if a.val > b.val:
                a, b = b, a
            a.next = self.mergeTwoLists(a.next, b)
        return a or b
```
- Performance
  - Runtime: 36 ms, faster than 62.84% of Python3 online submissions for Merge Two Sorted Lists.
  - Memory Usage: 13 MB, less than 96.69% of Python3 online submissions for Merge Two Sorted Lists.
