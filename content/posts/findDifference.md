+++
title = "First Bad Version"
date = "2020-05-02"
author = "Benjamin Cai"
description = "Leetcode question first bad version"
showFullContent = false
+++


## find Difference
```Python
class Solution(object):
    """
    dictionary
    """
    def findTheDifference(self, s, t):
        dic = {}
        for ch in s:
            dic[ch] = dic.get(ch, 0) + 1
        for ch in t:
            if dic.get(ch, 0) == 0:
                return ch
            else:
                dic[ch] -= 1

class Solution(object):
    """
    difference
    """
    def findTheDifference(self, s, t):
        diff = 0
        for i in range(len(s)):
            diff -= ord(s[i])
            diff += ord(t[i])
        diff += ord(t[-1])
        return chr(diff)


# Here we use ord can change char to ord ASCII number and chr can change it back


class Solution(object):
    """
    difference
    """
    def findTheDifference(self, s, t):
        diff = 0
        for i in range(len(s)):
            diff -= ord(s[i])
            diff += ord(t[i])
        diff += ord(t[-1])
        return chr(diff)
```