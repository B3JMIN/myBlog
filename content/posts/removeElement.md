+++
title = "27 Remove element"
date = "2020-04-20"
author = "Benjamin Cai"
description = "Leetcode"
showFullContent = false
+++


I plan to start working on leetcode

##27. Remove Element##

The question is remove the val in nums in place with the given value and list

Example:
```html
Given nums = [3,2,2,3], val = 3
return length = 2 but the array should be changed into [2,2], modifying in place
P.S. The array is passed by reference so modification to the array will be tested 
```

```Python
class Solution:
def removeElement(sef, nums:List[int], val:int) -> int:
    i = len(nums)
    while(nums.count(val) != 0):
        nums.remove(val)
        i = i-1
    return  i

```


#### what I learned ####
```Python
    list.count(val) 
    # can count the times val in the list
    list.remove(val)
    # remove the first element in the list

```

#### Other solutions

Two Pointer:
    The idea is use two pointer, one from the start, one from the end, everytime we find a value that si the target value we swap it with an item starting from the right. we decrement end each time as we know that the final item is the target value and only increment satrt once we know the value is ok. Once start reaches end we know all items after the target value so we can stop there.

```Python
def removeElement(self, nums, val):
    start, end = 0, len(nums) -1
    while start <= end:
        if nums[start] == val:
            nums[start], nums[end], end = nums[end], nums[start], end -1
        else:
            start += 1
    return start
    # Maybe using remove() is a better choice
```