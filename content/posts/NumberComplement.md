+++
title = "Number Complement"
date = "2020-05-04"
author = "Benjamin Cai"
description = "Leetcode"
showFullContent = false
+++


## Number Complement
Given a positive integer, output its complement number. The complement strategy is to flip the bits of its binary representation.

Example:
Input: 5
Output: 2
Explanation: The binary representation of 5 is 101 (no leading zero bits), and its complement is 010. So you need to output 2.

My submission:
```Python
class Solution:
    def findComplement(self, num: int) -> int:
        length = len(bin(num)) - 2
        return 2 ** length - num -1
```

some other methods in discussions: using bitwise shift
```Python
class Solution(object):
    def findComplement(self, num):
        i = 1
        while i <= num:
            i = i << 1
        return (i - 1) ^ num
```