# maximum product subarray/submissions/2027292932

**Platform:** LeetCode  
**Date:** 2026-06-09  

## Solution

```
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int bestmax=nums[0];
        int bestmin=nums[0];
        int ans=nums[0];
        for(int i=0;i<nums.size();i++){
            int c1=nums[i];
            int c2=nums[i]*bestmax;
            int c3=nums[i]*bestmin;
            bestmax=max(c1,max(c2,c3));
            bestmin=min(c1,min(c2,c3));
            ans=min(c1,min(c2,c3));
        }
        return ans;
    }
};
```
