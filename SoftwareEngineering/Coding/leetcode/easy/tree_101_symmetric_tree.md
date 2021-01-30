# Symmetric Tree

## Description
Given a binary tree, check whether it is a mirror of itself (ie, symmetric around its center).

For example, this binary tree [1,2,2,3,4,4,3] is symmetric:
```
    1
   / \
  2   2
 / \ / \
3  4 4  3
```
But the following [1,2,2,null,3,null,3] is not:
```
    1
   / \
  2   2
   \   \
   3    3
```

Note:
Bonus points if you could solve it both recursively and iteratively.

## My solution
- Code
```
class Solution:
    def isSymmetric(self, root):
        if not root:
            return True
        stack = [root]
        while len(stack) > 0:
            nodes, vals = [], []
            for node in stack:
                if node.left:
                    nodes.append(node.left)
                    vals.append(node.left.val)
                else:
                    vals.append(None)
                if node.right:
                    nodes.append(node.right)
                    vals.append(node.right.val)
                else:
                    vals.append(None)
            if vals != vals[::-1]:
                return False
            stack = nodes
        return True
```
- Performance
  - Runtime: 32 ms, faster than 69.34% of Python3 online submissions for Symmetric Tree.
  - Memory Usage: 14 MB, less than 5.17% of Python3 online submissions for Symmetric Tree.

## Optimal solution
- Code : recursive
```
def isSymmetric(self, root):
        def isSym(L,R):
            if L and R and L.val == R.val: 
                return isSym(L.left, R.right) and isSym(L.right, R.left)
            return L == R
        return not root or isSym(root.left, root.right)
```
- Performance
  - Runtime: 36 ms, faster than 31.91% of Python3 online submissions for Symmetric Tree.
  - Memory Usage: 13.9 MB, less than 5.17% of Python3 online submissions for Symmetric Tree.

- Code : iterative
```
def isSymmetric(self, root):
    queue = [root]
    while queue:
        values = [i.val if i else None for i in queue]
        if values != values[::-1]: return False
        queue = [child for i in queue if i for child in (i.left, i.right)]
    return True
```
- Performance
  - Runtime: 32 ms, faster than 69.34% of Python3 online submissions for Symmetric Tree.
  - Memory Usage: 14 MB, less than 5.17% of Python3 online submissions for Symmetric Tree.
