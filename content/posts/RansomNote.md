+++
title = "Ransom Note"
date = "2020-05-03"
author = "Benjamin Cai"
description = "leetcode Ransom Note"
showFullContent = false
+++


## Ransom Note
Given an arbitrary ransom note string and another string containing letters from all the magazines, write a function that will return true if the ransom note can be constructed from the magazines ; otherwise, it will return false.

Each letter in the magazine string can only be used once in your ransom note.

Note:
You may assume that both strings contain only lowercase letters.

canConstruct("a", "b") -> false
canConstruct("aa", "ab") -> false
canConstruct("aa", "aab") -> true

**The key is using set and count in python**

Not only we need to make sure all the element in ransomNote has in magazine, but also we need to make sure their numbers are less than it in magazine:
```Python
class Solution:
    def canConstruct(self, ransomNote:str, magazine:str) -> bool:
    for i in set(ransomNote):
        if ransomNote.count(i) > magazine.count(i):
            return False
    return True
```
set is unordered collections of **unique** elements
then we just count the number of set element in both string


There is some other [Java solutions](https://leetcode.com/problems/ransom-note/discuss/85801/Share-My-Easy-to-Understand-5-lines-of-Java-Code-13ms-beats-96)