# 75 DAYS GFG POTD ARTICLE CHALLENGE CHALLENGE(DAY 2/75)

**Platform:** GeeksForGeeks  
**Date:** 2026-06-04  

## Solution

```
class Solution {
  public:
    int longestKSubstr(string &s, int k) {
        // code here
        unordered_map<char,int>f;
        int low=0,high=0;
        int res=INT_MIN;
        for(high=0;high<s.length();high++){
            f[s[high]]++;
            if(f.size()==k){
                int len=high-low+1;
                res=max(res,len);
            }
            while(f.size()>k){
                f[s[low]]--;
                if(f[s[low]]==0)
                f.erase(s[low]);
                low++;
            }
        }
        if(res!=INT_MIN)
        return res;
        else
        return -1;
    }
};
```
