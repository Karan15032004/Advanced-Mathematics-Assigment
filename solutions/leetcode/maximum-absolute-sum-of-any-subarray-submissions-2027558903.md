# maximum absolute sum of any subarray/submissions/2027558903

**Platform:** LeetCode  
**Date:** 2026-06-09  

## Solution

```
class Solution {
public:
    int maxAbsoluteSum(vector<int>& nums) {
        int best_max=nums[0],best_min=nums[0],ans_max=nums[0],ans_min=nums[0];
        for(int i=1;i<nums.size();i++){
            int c1=nums[i];
            int c2=nums[i]+best_max;
            int c3=nums[i]+best_min;
            best_max=max(c1,c2);
            best_min=min(c1,c3);
            ans_max=max(ans_max,best_max);
            ans_min=min(ans_min,best_min);
        }
        if(abs(ans_min)>ans_max)
        return abs(ans_min);
        else
        return ans_max;
    }
};
```
