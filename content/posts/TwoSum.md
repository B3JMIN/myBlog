+++
title = "Two Sum"
date = "2020-04-22"
author = "Benjamin Cai"
description = "leetcode"
showFullContent = false
+++

### [1\. Two Sum](https://leetcode.com/problems/two-sum/)

Difficulty: **Easy**


Given an array of integers, return **indices** of the two numbers such that they add up to a specific target.

You may assume that each input would have **_exactly_** one solution, and you may not use the _same_ element twice.

**Example:**

```
Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].
```


#### Solution

Language: **Python3**

```Python
class Solution:
    def twoSum(self, nums: List[int], target: int) -> List[int]:
        res = []
        for i in nums:
            other = target - i
            if nums.count(other) and nums.index(i) != nums.index(other): 
                if res.count(nums.index(i)) not in res: 
                    res.append(nums.index(i))
                    res.append(nums.index(other))
        return res
    # This doesnt works since it cannot output duplicate value inthe list
    # for [3,3], it will return [] instead of [0,1]
```

```Python
# Here is my second thought on how to solve, we can 
class Solution:
    def twoSum(self, nums, target):
        for i in range(len(nums)):
            if target-nums[i] in nums[i+1:]:
                return [i,nums.index(target-nums[i],i+1)]
    
# This way we start from the i+1 position, just to ensure it's in the later list...
# another key point is list.index(element, start, end); here we emphasize the starting point to search for the element to aviod duplicated
```

Or we can use a dictionary, store the value first, then when we get in agian as a key we can simply return them 
```Python
class Solution(object):
    def twoSum(self, nums, target):
        if len(nums) <= 1:
            return False
        buff_dict = {}
        for i in range(len(nums)):
            if nums[i] in buff_dict:
                return [buff_dict[nums[i]], i]
            else:
            buff_dict[target-nums[i]] = i
        # Or Similar solution:
        dict ={}
        for i, num in enumerate(nums):
            if num in dict:
                return [dict[num], i]
            else:
                dict[target -num] = i
```

#### Conclusion
should consider more to avoid the duplciate situation, using dict or iterate from the i + 1