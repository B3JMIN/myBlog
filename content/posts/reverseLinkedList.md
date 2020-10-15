+++
title = "206 Reverse Linked List"
date = "2020-04-22"
author = "Benjamin Cai"
description = "leetcode"
showFullContent = false
+++

## How to reverse a Linked List

 ### [206\. Reverse Linked List](https://leetcode.com/problems/reverse-linked-list/)

Difficulty: **Easy**


Reverse a singly linked list.

**Example:**

```
Input: 1->2->3->4->5->NULL
Output: 5->4->3->2->1->NULL
```

**Follow up:**

A linked list can be reversed either iteratively or recursively. Could you implement both?


#### Solution

Language: **Python3**

```Python
# Definition for singly-linked list.
# class ListNode:
#     def __init__(self, x):
#         self.val = x
#         self.next = None
​
class Solution:
    def reverseList(self, head: ListNode) -> ListNode:
        prev = None
        while head:
            current = head
            head = head.next
            current.next = prev
            prev = current
        return prev
    
# basic idea of how to iteratively reverse a linked list is:
# each time iterate the head, let head point to the prev one
```


### Reverse Linkedlist recursively
```Python
class Solution:
    def reverseList(self, head):
    """
    :type head: ListNode
    rtype: ListNode
    """
    cur, prev = head, None
    while cur:
        cur.next, prev, cur = prev, cur, cur.next
    return prev
```


## Conclusion
Iterative and Recursively difference:
Iterative continuously calles functions while recursively calles itself 