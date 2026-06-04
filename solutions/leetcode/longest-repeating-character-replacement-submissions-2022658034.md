# longest repeating character replacement/submissions/2022658034

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int maxcount(vector<int> f){
        int max_f=f[0];
        for(int i=1;i<f.size();i++)
        max_f=max(max_f,f[i]);
        return max_f;
    }
    int characterReplacement(string s, int k) {
        int low=0,high=0;//dynamic window hai
        int res=INT_MIN;
        if(s.length()==0)
        return 0;
        vector<int>f(256,0);
        for(high=0;high<s.length();high++){
            f[s[high]]++;
            int len=high-low+1;
            int freq=maxcount(f);
            int diff=len-freq;
            while(diff>k){
                f[s[low]]--;
                low++;
                freq=maxcount(f);
                len=high-low+1;
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
