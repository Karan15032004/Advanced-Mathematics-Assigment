# subarray sums divisible by k/submissions/2029547894

**Platform:** LeetCode  
**Date:** 2026-06-11  

## Solution

```
class Solution {
public:
    int subarraysDivByK(vector<int>& nums, int k) {
        int sum=0,c=0;
        unordered_map<int,int>f;
        f[0]=1;
        for(int i=0;i<nums.size();i++){
            sum+=nums[i];
            int rem=sum%k;
            c+=f[rem];
            f[rem]++;
        }
        return c;
    }
};
```
