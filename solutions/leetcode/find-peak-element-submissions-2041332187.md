# find peak element/submissions/2041332187

**Platform:** LeetCode  
**Date:** 2026-06-21  

## Solution

```
class Solution {
public:
    int findPeakElement(vector<int>& nums) {
        int n=nums.size();
        if(n==0)
        return -1;
        int low=0,high=n-1,mid=-1;
        while(low<=high){
            mid=low+(high-low)/2;
            int el=nums[mid];
            if(mid==n-1)
            if(mid==0)
            return 0;
            return n-1;
            if(el>nums[mid+1]&&el>nums[mid-1])
            return mid;
            else if(el>nums[mid+1]&&el<nums[mid-1])
            high=mid-1;
            else if(el>nums[mid-1]&&el<nums[mid+1])
            low=mid+1;
            else
            low=mid+1;
        }
        return mid;
    }
};
```
