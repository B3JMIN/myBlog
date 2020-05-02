+++
title = "First Bad Version"
date = "2020-05-02"
author = "Benjamin Cai"
description = "Leetcode question first bad version"
showFullContent = false
+++


### First Bad version
**Question**
You are a product manager, here is a array from 1 to n about the version in your product. you want to find the first bad version
there is one provided function:
`bool isBadVersion(version)` which will return whether version is bad. Implement a function to find the first bad version. You should minimize the number of calls to the API.

Example:
`Given n = 5 and version 4 is the first bad version.`


```Python
class Solution:
    def firstBadVersion(self,n):
    """
    :type n: int
    :rtype: int
    """
    
```

Analysis:
    here is a simple search question, we can use iteration all elements but that will cause `runtime error`

1. binary search is one of the solutions
```Java
public int firstBadVersion(int n){
    int start = 1, end = n;
    while(start < end){
        int mid = start + (end - start) / 2;
        if (!isBadverison(mid)) start = mid + 1
        else end = start
    }
    return start
}
```

binary search