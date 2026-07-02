# valid palindrome ii/submissions/2053505760

**Platform:** LeetCode  
**Date:** 2026-07-02  

## Solution

```
class Solution {
public:
    bool validPalindrome(string s) {
        int k=0,i=0,j=s.length()-1;
        while(i<j){
            if(s[i]==s[j])
            {
                i++;
                j--;
            }
            else if(s[i]!=s[j]&&k<1){
                k++;
                if(s[i+1]==s[j])
                i++;
                else if(s[j-1]==s[i])
                j--;
            }
                else if(s[i]!=s[j]&&k>=1){
                return false;
            }
        }
        return true;
    }
};
```
