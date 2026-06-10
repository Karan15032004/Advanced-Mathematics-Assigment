# find pivot index/submissions/2028430140

**Platform:** LeetCode  
**Date:** 2026-06-10  

## Solution

```
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int left=0,sum=0;
        for(int i=0;i<nums.size();i++)
        sum+=nums[i];
        int right=sum-nums[0];
        if(right==0)
        return 0;
        for(int i=1;i<nums.size();i++){
            left+=nums[i-1];
            right=sum-left-nums[i];
            if(left==right)
            return i;
        }
        return -1;
    }
};
```
