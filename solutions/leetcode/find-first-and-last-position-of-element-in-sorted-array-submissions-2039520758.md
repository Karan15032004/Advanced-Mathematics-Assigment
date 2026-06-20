# find first and last position of element in sorted array/submissions/2039520758

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    vector<int> searchRange(vector<int>& nums, int target) {
        int low=0,n=nums.size();
        int high=n-1,first=-1,last=-1;
        if(nums.size()==0)
        return {-1,-1};
        while(low<=high){
            int mid=(low+high)/2;
            if(nums[mid]>target)
            high=mid-1;
            else if(nums[mid]<target)
            low=mid+1;
            else{
                first=mid;
                high=mid-1;
            }
        }
        low=0,high=n-1;
            while(low<=high){
            int mid=(low+high)/2;
            if(nums[mid]>target)
            high=mid-1;
            else if(nums[mid]<target)
            low=mid+1;
            else{
                last=mid;
                low=mid+1;
            }
        }
        return {first,last};
    }
};
```
