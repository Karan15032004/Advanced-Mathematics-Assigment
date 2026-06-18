# first unique character in a string/submissions/2037269792

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    int firstUniqChar(string s) {
        unordered_map<char,int>f;
        for(int i=0;i<s.length();i++){
        f[s[i]]++;
        }
        for(int i=0;i<s.length();i++){
            if(f[s[i]]==1)
            return i;
        }
        return -1;
    }
};
```
