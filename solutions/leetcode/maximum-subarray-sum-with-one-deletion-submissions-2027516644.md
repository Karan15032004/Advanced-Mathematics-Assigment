# maximum subarray sum with one deletion/submissions/2027516644

**Platform:** LeetCode  
**Date:** 2026-06-09  

## Solution

```
class Solution {
public:
    int maximumSum(vector<int>& arr) {
        int ans=arr[0],best=arr[0];
        int biz=-1;
        for(int i=1;i<arr.size();i++){
            int c1=arr[i];
            int c2=arr[i]+max(best,biz);
            biz=best;
            best=max(c1,c2);
            ans=max(ans,max(biz,best));
        }
        return ans;
    }
};
```
