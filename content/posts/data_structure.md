+++
title = "Data Structure"
date = "2020-04-27"
author = "Benjamin Cai"
description = "Notes I have before about basic data structure"
showFullContent = false
+++

**stack** 

in python: **LIFO**(last in first out)

some methods of python stack:

Stack() -- create a python stack

push(item)

pop()

peek() --  return the last one 

isEmpty() and size()

**Queue**

FIFO, some implementation: line up printer and hot potatoes

also we have a **deque**, this can be FIFO or LIFO

List: 

ordered list and unordered list: linked list and *normal list* 





**Recursion:**

calculate the sum of the list: 

```python
def listsum(numList):
  if len(numList) == 1:
    return numList[0]
  else:
    return numList[0] + listsum(numlist[1:])
   
```

Sorting algo:

merge sorting uses divide and conquer

quick sort as well:

quick sort move the element depending on the compared value with the pivot 





Learn tree as a data structure 

```python
class BinaryTree:
    def __init__(self,rootObj):
        self.key = rootObj
        self.leftChild = None
        self.rightChild = None

    def insertLeft(self,newNode):
        if self.leftChild == None:
            self.leftChild = BinaryTree(newNode)
        else:
            t = BinaryTree(newNode)
            t.leftChild = self.leftChild
            self.leftChild = t

    def insertRight(self,newNode):
        if self.rightChild == None:
            self.rightChild = BinaryTree(newNode)
        else:
            t = BinaryTree(newNode)
            t.rightChild = self.rightChild
            self.rightChild = t


    def getRightChild(self):
        return self.rightChild

    def getLeftChild(self):
        return self.leftChild

    def setRootVal(self,obj):
        self.key = obj

    def getRootVal(self):
        return self.key

```

Parse tree in real world: do calculation: and we can then replace sub tree with a node

operator and parathesis can be used to added to the tree



Tree traversal : preorder, inorder, postorder

Binary heap

binary search tree