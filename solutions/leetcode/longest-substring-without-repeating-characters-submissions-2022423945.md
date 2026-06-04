# longest substring without repeating characters/submissions/2022423945

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        if(s.length()==0)
        return 0;
        unordered_map<char,int>f;
        int low=0,high=0,freq=INT_MIN,res=INT_MIN;
        for(high=0;high<s.length();high++){
            f[s[high]]++;
            for(auto it=f.begin();it!=f.end();it++){
                if(it->second==2){
                    f[s[low]]--;
                    if(f[s[low]]==0)
                    f.erase(s[low]);
                    low++;
                }
            }
            for(auto it=f.begin();it!=f.end();it++){
              freq=max(freq,it->second);  //checks if any character has freq=2
            }
            if(freq==1){
                int len=high-low+1;
                res=max(len,res);
            }
            else
            {
            f[s[low]]--;
            if(f[s[low]]==0)
            f.erase(s[low]);
            low++;  
            }
        }
        return res;
    }
};
```
