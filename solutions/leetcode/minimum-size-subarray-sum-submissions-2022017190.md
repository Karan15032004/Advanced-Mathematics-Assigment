# minimum size subarray sum/submissions/2022017190

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int low=0,high=0;
        int sum=0,res=INT_MAX;
            while(high<nums.size()){
                sum+=nums[high];
                while(sum>=target){
                    int len=high-low+1;
                    res=min(res,len);
                    low++;
                    sum-=nums[low-1];
                }
                high++;
            }
            return res;
    }
};
```
