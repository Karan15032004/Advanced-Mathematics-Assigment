# search in rotated sorted array/submissions/2041860636

**Platform:** LeetCode  
**Date:** 2026-06-22  

## Solution

```
class Solution {
public:
    int search(vector<int>& nums, int target) {
        int n=nums.size();
        if(n==0)
        return -1;
        if(n==1 && target!=nums[0])
        return -1;
        if(n==1 && target==nums[0])
        return 0;
        int low=0,high=n-1;
        if(nums[0]<nums[n-1]){
            return binarysearch(nums,target);
        }
        while(low<=high){
            int mid=low+(high-low)/2;
            if(nums[mid]==target)
            return mid;
            else if(nums[mid]>target){
                if(nums[mid]>nums[n-1])
                low=mid+1;
                else
                high=mid-1;
            }
            else{
                if(nums[mid]>nums[n-1])
                low=mid+1;
                else
                high=mid-1;
            }
        }
        return -1;
        
    }
    int binarysearch(vector<int> nums,int target){
    int low=0,high=nums.size()-1;
    while(low<=high){
        int mid=low+(high-low)/2;
        if(nums[mid]==target)
        return mid;
        else if(nums[mid]>target)
        high=mid-1;
        else
        low=mid+1;
    }
    return -1;
            }
};
```
