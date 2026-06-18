# maximum number of balloons/submissions/2037325496

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    int maxNumberOfBalloons(string text) {
        //string needed="balloon";
        unordered_map<char,int>have,need;
        for(int i=0;i<text.length();i++)
        have[text[i]]++;
        need['b']=1;
        need['a']=1;
        need['l']=2;
        need['o']=2;
        need['n']=1;
        int res=INT_MAX;
        for(auto i:need){
            char ch=i.first;
            int val=i.second;
            int have_val=have[ch];
            int ans=have_val/val;
            res=min(res,ans);
        }
        return res;
    }
};
```
