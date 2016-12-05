---
title: 01-Two-Sum
tags: 新建,模板,小书匠
grammar_cjkRuby: true
---

# source

[1. Two Sum](https://leetcode.com/problems/two-sum/)


## similiar problem

[lintcode56 tow sum](http://www.lintcode.com/en/problem/two-sum/)

[lint138-Subarray-Sum](https://github.com/DragonFive/Leetcode/blob/master/String/lint138-Subarray-Sum.md)
# solution

```cpp
    vector<int> twoSum(vector<int> &nums, int target) {
        // write your code here
        unordered_map<int, int> numsIndexMap;
        const int size = nums.size();
        vector<int> ret;
        // 建立哈希表
        for (int i = 0; i < size; ++i)
        {
            numsIndexMap[nums[i]] = i + 1;
        }
        // 寻找配对
        for (int i = 0; i < size; i++)
            if (numsIndexMap.find(target - nums[i]) != numsIndexMap.end() && i != numsIndexMap[target - nums[i]])
            {
                ret.push_back(i + 1);
                ret.push_back(numsIndexMap[target - nums[i]]);
                break;
            }
         return ret;       
        
    }
```