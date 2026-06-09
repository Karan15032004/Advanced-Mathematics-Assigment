# maximum product subarray/submissions/2027298178

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
        if(nums.size()==0)
        return 0;
        if(nums.size()==1)
        return nums[0];


        for(int i=0;i<nums.size();i++){
            if(nums[i]==0)
            return 0;
            int c1=nums[i];
            int c2=nums[i]*bestmax;
            int c3=nums[i]*bestmin;
            bestmax=max(c1,max(c2,c3));
            bestmin=min(c1,min(c2,c3));
            ans=max(ans,bestmax);
        }
        return ans;
    }
};
```
