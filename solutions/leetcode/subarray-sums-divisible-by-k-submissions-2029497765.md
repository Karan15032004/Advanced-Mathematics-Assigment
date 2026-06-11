# subarray sums divisible by k/submissions/2029497765

**Platform:** LeetCode  
**Date:** 2026-06-11  

## Solution

```
class Solution {
public:
    int subarraysDivByK(vector<int>& nums, int k) {
      unordered_map<int,int>f;
      f[0]=1;
      int sum=0,c=0;
      for(int i=0;i<nums.size();i++){
        sum=(sum+nums[i]%k+k)%k;

        c+=f[sum];
        f[sum]++;
      }  
      return c;
    }
};
```
