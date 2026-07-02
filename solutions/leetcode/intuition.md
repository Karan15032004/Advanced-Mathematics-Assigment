# 🧠 Intuition

**Platform:** LeetCode  
**Date:** 2026-07-02  

## Solution

```
class Solution {
public:
bool ispali(string s,int i,int j){
    while(i<j){
        if(s[i]!=s[j])
        return false;
        i++;j--;
    }
    return true;
}
    bool validPalindrome(string s) {
        int k=0,i=0,j=s.length()-1;
        while(i<j){
        if(s[i]!=s[j])
        return ispali(s,i+1,j)||ispali(s,i,j-1);
        i++;j--;
    }
    return true;
    }
};
```
