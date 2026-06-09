# maximum subarray/submissions/2027277606

**Platform:** LeetCode  
**Date:** 2026-06-09  

## Solution

```
class Solution {
public:
    int maxSubArray(vector<int>& nums) {
        int bestending=nums[0];
        int ans=nums[0];
        if(nums.size()==1)
        return nums[0];
        if(nums.size()==0)
        return 0;
        for(int i=1;i<nums.size();i++){
            int c1=nums[i];
            int c2=nums[i]+bestending;
            bestending=max(c1,c2);
            ans=max(ans,bestending);
        }
        return ans;
    }
};
```
