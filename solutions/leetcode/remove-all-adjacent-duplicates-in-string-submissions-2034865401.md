# remove all adjacent duplicates in string/submissions/2034865401

**Platform:** LeetCode  
**Date:** 2026-06-16  

## Solution

```
class Solution {
public:
    string removeDuplicates(string s) {
        stack<char>st;
        if(s.length()==0||s.length()==1)
        return s;
        //st.push(s[0]);
        for(int i=0;i<s.length();i++){
            if(st.empty())
            st.push(s[i]);
            else if(s[i]==st.top())
            st.pop();
            else{
                st.push(s[i]);
            }
        }
        string ans="";
        if(st.empty())
        return "";
        else{
        while(!st.empty()){
            ans=st.top()+ans;
            st.pop();
        }}
        return ans;
    }
};
```
