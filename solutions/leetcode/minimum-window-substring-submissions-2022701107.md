# minimum window substring/submissions/2022701107

**Platform:** LeetCode  
**Date:** 2026-06-04  

## Solution

```
class Solution {
public:
bool difference(vector<int>s1,vector<int>s2){
    for(int i=0;i<256;i++){
        s1[i]-=s2[i];
        if(s1[i]<0)
        return false;
    }
    return true;
}
    string minWindow(string s, string t) {
        if(t.length()>s.length())
        return "";
        vector<int>s2(256,0);
        int res=INT_MAX;
        for(int ch=0;ch<t.length();ch++){
            s2[t[ch]]++;
        }
        int low=0;int high=0;
        unordered_map<int,string>f;
        for(high=0;high<s.length();high++){
            string ans="";
            vector<int>s1(256,0);
            for(int i=low;i<=high;i++){
            ans+=s[i];
            s1[s[i]]++;
            }
            int len=ans.length();
            while(difference(s1,s2)){
                f[len]=ans;
                res=min(len,res);
                s1[s[low]]--;
                low++;
                vector<int> s1(256,0);
                for(int i=low;i<high;i++){
                    s1[s[i]]++;
                }
            }
        }
        return f[res];
    }
};
```
