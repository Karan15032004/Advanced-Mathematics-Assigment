# ransom note/submissions/2037295971

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    bool canConstruct(string ransomNote, string magazine) {
        unordered_map<char,int>have,need;
        for(int i=0;i<ransomNote.size();i++)
        need[ransomNote[i]]++;
        for(int i=0;i<magazine.size();i++)
        have[magazine[i]]++;
        for(auto i:need){
            char ch=i.first;
            int val=i.second;
            if(have[ch]<val)
            return false;
        }
        return true;

    }
};
```
