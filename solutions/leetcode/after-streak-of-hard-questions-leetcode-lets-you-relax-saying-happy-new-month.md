# After streak of hard questions, leetcode lets you relax. Saying happy new month.

**Platform:** LeetCode  
**Date:** 2026-06-20  

## Solution

```
class Solution {
public:
    int search(vector<int>& nums, int target) {
        if(nums.size()==0)
        return -1;
        int low=0,high=nums.size()-1;
        while(low<=high){
            int mid=low+(high-low)/2;
            if(nums[mid]>target)
            high=mid-1;
            else if(nums[mid]<target)
            low=mid+1;
            else
            return mid;
        }
        return -1;
    }
};
```
