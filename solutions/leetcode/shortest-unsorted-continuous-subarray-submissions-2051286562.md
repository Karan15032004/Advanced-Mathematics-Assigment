# shortest unsorted continuous subarray/submissions/2051286562

**Platform:** LeetCode  
**Date:** 2026-06-30  

## Solution

```
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
        int n=nums.size(),maxi=nums[0],mini=nums[n-1],start=n-1,end=0;
        for(int i=1;i<n;i++){
            maxi=max(maxi,nums[i]);
            if(nums[i]<maxi)
            end=i;
        }
        for(int i=n-2;i>=0;i--){
            mini=min(mini,nums[i]);
            if(nums[i]>mini)
            start=i;
        }
        if(end==0)
        return 0;
        else
        return (end-start+1);
    }
};
```
