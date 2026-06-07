# shortest unsorted continuous subarray/submissions/2025352525

**Platform:** LeetCode  
**Date:** 2026-06-07  

## Solution

```
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
        if(nums.size()==0||nums.size()==1)
        return 0;
        int start=0,end=nums.size()-1;
        while(start<nums.size()-1){
            if(nums[start]>nums[start+1])
            break;
            start++;
        }
         while(end>start){
            if(nums[end]<nums[end-1])
            break;
            end--;        
            }
            if(start==end)
            return 0;
            else
            return (end-start+1);
           }
};
```
