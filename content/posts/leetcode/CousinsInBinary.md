+++
title = "Cousins in Binary Tree"
date = "2020-05-07"
author = "Benjamin Cai"
description = "Leetcode question Cousins in Binary Tree"
showFullContent = false
+++



### [DFS and BFS understanding](http://mishadoff.com/blog/dfs-on-binary-tree-array/)



Here is the question:
In a binary tree, the root node is at depth 0, and children of each depth k node are at depth k+1.

Two nodes of a binary tree are cousins if they have the same depth, but have different parents.

We are given the root of a binary tree with unique values, and the values x and y of two different nodes in the tree.

Return true if and only if the nodes corresponding to the values x and y are cousins.

 

Example 1:


Input: root = [1,2,3,4], x = 4, y = 3
Output: false
Example 2:


Input: root = [1,2,3,null,4,null,5], x = 5, y = 4
Output: true
Example 3:



Input: root = [1,2,3,null,4], x = 2, y = 3
Output: false
 

Note:

The number of nodes in the tree will be between 2 and 100.
Each node has a unique integer value from 1 to 100.
 

 My Solution:
 #### DFS(Depth first search)
 ```Python
 # Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isCousins(self, root: TreeNode, x: int, y: int) -> bool:
        def dfs(node:TreeNode, parent:TreeNode, depth:int):
            if not node or len(results) == 2:
                return
            else:
                if node.val == x  or node.val == y:
                    results.append((parent, depth))
                dfs(node.left, node, depth + 1)
                dfs(node.right, node, depth + 1)
                
                
        results = []
        dfs(root, None, 0)
        return results[0][0] != results[1][0] and results[0][1] == results[1][1]
    
# define a def function to append the parent and depth
# and recursively call the funtion till we find the two nodes
 ```


#### BFS(breadth first search)

```Python
class Solution(object):
    def isCousins(self,root,x,y):
        nodes = {}
        level = [(root, 0, 0)]
        while level:
            cur, parent, depth = level.pop()
            nodes[cur.val ] = [parent, depth]

            if cur.left:
                level.append((cur.left, cur.val, depth + 1)
            if cur.right:
                level.apend(cur.right, cur.val, depth + 1)
        print(nodes)
        return nodes[x][1] == nodes[y][1] and (nodes[x][0] != nodes[y][0])
```