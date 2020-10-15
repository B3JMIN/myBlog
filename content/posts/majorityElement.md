+++
title = "Majority Element"
date = "2020-05-04"
author = "Benjamin Cai"
description = "Leetcode"
showFullContent = false
+++

Given an array of size n, find the majority element. The majority element is the element that appears more than ⌊ n/2 ⌋ times.

You may assume that the array is non-empty and the majority element always exist in the array.

Example1:
Input: [3,2,3]
Output: 3

Example2:
Input: [2,2,1,1,1,2,2]
Output: 2

My solution:
```Python
class Solution:
    def majorityElement(self, nums: List[int]) -> int:
        length = len(nums)
        for num in set(nums):
            if nums.count(num) >= (length /2):
                return num
            
# beats 95.6% of submission     
#check each element in set
```

### Other Solutions(Hashmap):
We can use a `Hashmap` that maps elements to counts in order to count occurrenc in linear time by looping over `nums`

```Python
class Solution:
    def majorityElement(self, nums):
    counts = collections.Counter(nums)
    return max(counts.keys(), key=counts.get)
```


Thought:
Even my submission is faster than 95%, it still takes O(n^2) time.
hashmap is obviusly better