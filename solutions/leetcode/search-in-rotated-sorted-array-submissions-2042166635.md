# search in rotated sorted array/submissions/2042166635

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    int binarysearch(vector<int>nums,int target,int start,int end){
        while(start<=end){
            int mid=start+(end-start)/2;
            if(nums[mid]==target)
            return mid;
            else if(nums[mid]<target){
                start=mid+1;
            }
            else
            end=mid-1;
        }
        return -1;
    }
    int search(vector<int>& nums, int target) {
        int n=nums.size(),res=-1;
        if(n==0)
        return -1;
        if(n==1){
            if(nums[0]==target)
            return 0;
            else
            return -1;
        }
        if(nums[0]<nums[n-1])
        return binarysearch(nums,target,0,n-1);
        int low=0,high=n-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(nums[mid]==target)
            return mid;
            if(nums[mid]<=nums[n-1]){
                res=mid;
                high=mid-1;
            }
            else{
                low=mid+1;
            }
        }
        if(target>nums[n-1])
        return binarysearch(nums,target,0,res-1);
        else if(target==nums[n-1])
        return n-1;
        else
        return binarysearch(nums,target,res,n-1);
    }
};
```
