# fruit into baskets

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int totalFruit(vector<int>& fruits) {
        unordered_map<int,int> f;
        if(fruits.size()==0)
        return 0;
        int low=0,high=0,len=1,res=INT_MIN;
        for(high=0;high<fruits.size();high++){
            f[s[high]]++;
            if(f.size()==2){
               len=high-low+1;
                res=max(res,len);
            }
            while(f.size()>2){
                f[fruits[low]]--;
                if(f[fruits[low]]==0)
                f.erase(fruits[low]);
                low++:
            }
        }
        return res;
    }
};
```
