# LeetCode解题思路

[TOC]



## Easy

### 1.  Two Sum

**题目描述**

给定一个整数数组和一个目标值，找出数组中和为目标值的两个数。 

你可以假设每个输入只对应一种答案，且同样的元素不能被重复利用。 

示例：

给定 ` nums = [2, 7, 11, 15], target = 9 `

因为 `nums[0] + nums[1] = 2 + 7 = 9 `

所以返回 `[0, 1] `

**分析**

1. 暴力处理，逐一检验，复杂度为$$O(n^2)$$，运行会超时。
2. 散列表（hash)，用哈希表，匹配每个数对应的下标，时间复杂度为 $$O(n)$$ 

**代码**

以下两种方法的原理都是一样的，只是实现的代码不同

```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        
        # enumerate（）函数用于将一个可遍历的数据对象组合为一个索引序列
        # 同时列出数据和数据下标，一般用在 for 循环当中。
        
        lookup = {}        # 建立一个字典，即散列表。用来查询下标 
        for i, num in enumerate(nums):
            if target - num in lookup:
                return [lookup[target - num], i]
            lookup[num] = i        # 存放已经减去的数和其在原序列中的下标

    def twoSum2(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        for i in nums:
            j = target - i
            tmp_nums_start_index = nums.index(i) + 1
            tmp_nums = nums[tmp_nums_start_index:]
            if j in tmp_nums:
                return [nums.index(i), tmp_nums_start_index + tmp_nums.index(j)]


if __name__ == '__main__':
    print(Solution().twoSum((2, 7, 11, 15), 9))
    print(Solution().twoSum2((2, 7, 11, 15), 9))
```







## Medium

## Hard

