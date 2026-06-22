# Code

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    int findMin(vector<int>& nums) {
     int n=nums.size();
     if(n==0)
     return -1;
     if(n==1)
     return nums[0];
     if(nums[0]<nums[1]&&nums[0]<nums[n-1])
     return nums[0];
     int low=0,high=n-1,res=-1;
     while(low<=high){
        int mid=low+(high-low)/2;
        if(nums[mid]<=nums[n-1]){
            res=mid;
            high=mid-1;
        }
        else{
            low=mid+1;
        }
      }
       return nums[res];
    }
};
```
