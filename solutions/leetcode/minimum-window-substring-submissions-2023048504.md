# minimum window substring/submissions/2023048504

**Platform:** LeetCode  
**Date:** 2026-06-05  

## Solution

```
class Solution {
public:
    bool check(vector<int> s1,vector<int>t1){
        for(int i=0;i<256;i++){
            if(s1[i]<t1[i])
            return false;
        }
        return true;
    }
    string minWindow(string s, string t) {
        if(t.length()>s.length())
        return {};
        vector<int>s1(256,0),t1(256,0);
        for(int i=0;i<t.length();i++){
            t1[t[i]]++;
        }
        int high=0,low=0,res=INT_MAX,start=0;
        for(high=0;high<s.length();high++){
            s1[s[high]]++;
            while(check(s1,t1)){
            int len=high-low+1;
            if(len<res){
                res=len;
                start=low;
            }
            s1[s[low]]--;
            low++;
            }
        }
    if (res==INT_MAX)
    return {};
    else
    return s.substr(start,res);
    }
};
```
