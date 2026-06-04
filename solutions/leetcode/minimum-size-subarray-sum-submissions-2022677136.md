# minimum size subarray sum/submissions/2022677136

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int low=0,high=0;
        if(nums.size()==0)
        return 0;
        long long sum=0;int res=INT_MAX;
        for(high=0;high<nums.size();high++){
            sum+=nums[high];
            while(sum>=target){
                int len=high-low+1;
                res=min(res,len);
                sum-=nums[low];
                low++;
            }
        }
            if(res!=INT_MAX)
            return res;
            else return 0;
    }
};
```
