# [Data Structures] Trees: Is This A Binary Search Tree?

This Challenge can be found here: https://www.hackerrank.com/challenges/ctci-is-binary-search-tree.

The following is the description of the challenge.

>Given the root node of a binary tree, can you determine if it's also a binary search tree?

My submission with comments was the following.


```
""" Node is defined as
class node:
    def __init__(self, data):
        self.data = data
        self.left = None
        self.right = None
"""

import math

def help (root, minnum, maxnum):
    if root == None:
        return True                                                                                                           #if current node is the root of an empty subtree, it is a binary search tree
    
    else:                                                                                                                     #Otherwise,
        if root.left != None and (root.left.data >= maxnum or root.left.data>= root.data or root.left.data <=minnum):         # if left child of the current node exist and it is out of the current boundary restriction, that subtree is not a binary search tree
            return False                                                                                                      
    
        if root.right != None and (root.right.data <= root.data or root.right.data>=maxnum or root.right.data<=minnum):       # if right child of the current node exist and it is out of the current boundary restriction, that subtree is not a binary search tree
            return False

    minnum = min(minnum, root.data)                                                                                           # update min number to minimum of current node and current minimum
    maxnum = max(maxnum, root.data)                                                                                           # update max number to maximum of current node and current maximum
    return help(root.left, minnum, root.data) and help(root.right, root.data, maxnum)                                         # recursive calls with each child of the current node as nodes

def checkBST(root):
    return help(root, 0, math.pow(10,4))                                                                                      #call helper function with min and max of problem boundary
        
```
