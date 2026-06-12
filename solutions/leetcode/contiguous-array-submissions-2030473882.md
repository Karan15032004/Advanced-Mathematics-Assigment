# contiguous array/submissions/2030473882

**Platform:** LeetCode  
**Date:** 2026-06-12  

## Solution

```
class Solution {
public:
    int findMaxLength(vector<int>& nums) {
        unordered_map<int,int>f;
        int diff=0,ans=0;
        for(int i=0;i<nums.size();i++){
            if(nums[i]==0)
            diff++;
            else
            diff--;
            if(diff==0)
            ans=max(ans,i+1);
            else {
                auto it=f.find(diff);
                if (it!=f.end()){
                    ans=max(ans,i-(it->second));
                }
                else{
                    f[diff]=i;
                }
            }
        }
        return ans;
    }
};
```
