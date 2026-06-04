# max consecutive ones iii/submissions/2022665425

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int longestOnes(vector<int>& nums, int k) {
     int high=0,low=0,res=INT_MIN;
     if(nums.size()==0)
     return 0;
     vector<int>f(2,0);
     for(high=0;high<nums.size();high++){
        f[nums[high]]++;
        int len=high-low+1;
        int freq=f[1];
        int diff=len-freq;
        while(diff>k){
            f[nums[low]]--;
            low++;
            len--;
            freq=f[1];
            diff=len-freq;
        }
        if(diff<=k){
            res=max(res,len);
        }
     }
     return res;
    }
};
```
