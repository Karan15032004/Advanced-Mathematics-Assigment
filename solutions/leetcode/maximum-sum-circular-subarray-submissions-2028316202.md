# maximum sum circular subarray/submissions/2028316202

**Platform:** LeetCode  
**Date:** 2026-06-10  

## Solution

```
class Solution {
public:
    int maxSubarraySumCircular(vector<int>& nums) {
        int best_min=nums[0],ans_min=nums[0],ans_max=nums[0],best_max=nums[0],total=nums[0];
        for(int i=1;i<nums.size();i++){
            total+=nums[i];
            int c1=nums[i];
            int c2=nums[i]+best_max;
            int c3=nums[i]+best_min;
            best_max=max(c1,c2);
            best_min=min(c1,c3);
            ans_min=min(ans_min,best_min);
            ans_max=max(ans_max,best_max);
          }
          if(ans_max>(total-ans_min)){
            return ans_max;
          }
            else
            return (total-ans_min);
          
    }
};
```
