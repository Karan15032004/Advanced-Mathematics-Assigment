# minimum size subarray sum/submissions/2022054462

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int low=0,high=0;
        long long sum=0;int res=INT_MAX;
            while(high<nums.size()){
                sum+=nums[high];
                while(sum>=target){
                    int len=high-low+1;
                    res=min(res,len);
                    low++;
                    sum=sum-nums[low-1];
                }
                high++;
            }
            if(res!=INT_MAX)
            return res;
            else return 0;
    }
};
```
