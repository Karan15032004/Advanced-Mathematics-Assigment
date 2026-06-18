# Some Testcases if you are too lazy

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    int longestPalindrome(string s) {
        unordered_map<char,int>f;
        for(int i=0;i<s.length();i++){
            f[s[i]]++;
        }
    int ans=0,odd_count=0;
    for(auto it:f){
        int val=it.second;
        if(val%2==0)
        ans+=val;
        else{
        ans=ans+val-1;
        odd_count++;
        }
    }
    if(odd_count==0)
    return ans;
    else
    return ans+1;
    }
};
```
