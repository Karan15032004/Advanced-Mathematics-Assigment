# subarray sums divisible by k/submissions/2028485459

**Platform:** LeetCode  
**Date:** 2026-06-10  

## Solution

```
class Solution {
public:
    int subarraysDivByK(vector<int>& nums, int k) {
      unordered_map<int,int>f;
      f[0]=1;
      int sum=0,c=0;
      for(int i=0;i<nums.size();i++){
        sum+=nums[i];
        int q=sum%k;
        int freq=f[q];
        c+=freq;
        f[q]++;
      }  
      return c;
    }
};
```
