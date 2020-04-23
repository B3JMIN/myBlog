+++
title = "1394 Find Lucky Integer"
date = "2020-04-21T10:10:49-04:00"
author = "Benjamin Cai "
description = "leetcode"
showFullContent = false
+++

### [1394\. Find Lucky Integer in an Array](https://leetcode.com/problems/find-lucky-integer-in-an-array/)

Difficulty: **Easy**


Given an array of integers `arr`, a lucky integer is an integer which has a frequency in the array equal to its value.

Return _a lucky integer_ in the array. If there are multiple lucky integers return the **largest** of them. If there is no lucky integer return **-1**.

**Example 1:**

```
Input: arr = [2,2,3,4]
Output: 2
Explanation: The only lucky number in the array is 2 because frequency[2] == 2.
```

**Example 2:**

```
Input: arr = [1,2,2,3,3,3]
Output: 3
Explanation: 1, 2 and 3 are all lucky numbers, return the largest of them.
```

**Example 3:**

```
Input: arr = [2,2,2,3,3]
Output: -1
Explanation: There are no lucky numbers in the array.
```

**Example 4:**

```
Input: arr = [5]
Output: -1
```

**Example 5:**

```
Input: arr = [7,7,7,7,7,7,7]
Output: 7
```

**Constraints:**

*   `1 <= arr.length <= 500`
*   `1 <= arr[i] <= 500`


#### Solution

Language: **Python3**

```Python
class Solution:
    def findLucky(self, arr: List[int]) -> int:
        res = -1
        for x in arr:
            if(arr.count(x) == x):
                if x > res:
                    res = x
        return res
```

##Only faster than 6.0% of submission


fast one liner Python
```Python
class Solution:
    def findLucky(self, arr:List[int]) -> int:
        return max([k if k == v else -1 for k, v in collections.Counter(arr).items()])
```

[class collections.Counter([iterable-or-mapping])](https://docs.python.org/3/library/collections.html)

Counter is a dict subclass for counting hashable objects. It is collection where elements are stored as dictionary and their counts are stored as dictionary values