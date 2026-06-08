# Intuition

**Platform:** LeetCode  
**Date:** 2026-06-08  

## Solution

```
class Solution {
public:
string retstring(string s){
    stack<char> st;
    for(int i=0;i<s.length();i++){
        if(s[i]!='#')
        st.push(s[i]);
        else
        st.pop();
    }
    s="";
    while(!st.empty()){
    s+=st.top();
    st.pop();
    }
    return s;
}
    bool backspaceCompare(string s, string t) {
        s=retstring(s);
        t=retstring(t);
        if(s.length()!=t.length())
        return false;
        else{
            if(s==t)
            return true;
            else
            return false;
        }    }
};
```
