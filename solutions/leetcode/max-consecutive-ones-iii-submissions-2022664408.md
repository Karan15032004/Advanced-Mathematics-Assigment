# max consecutive ones iii/submissions/2022664408

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int maxcount(vector<int>f){;
        if (f[0]>f[1])
        return f[0];
        else
        return f[1];
    }
    int longestOnes(vector<int>& nums, int k) {
     int high=0,low=0,res=INT_MIN;
     if(nums.size()==0)
     return 0;
     vector<int>f(2,0);
     for(high=0;high<nums.size();high++){
        f[nums[high]]++;
        int len=high-low+1;
        int freq=maxcount(f);
        int diff=len-freq;
        while(diff>k){
            f[nums[low]]--;
            low++;
            len--;
            freq=maxcount(f);
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
