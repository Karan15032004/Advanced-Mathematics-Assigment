# remove k digits/submissions/2037784325

**Platform:** LeetCode  
**Date:** 2026-06-18  

## Solution

```
class Solution {
public:
    string removeKdigits(string nums, int k) {
        if(k>=nums.length())
        return "0";
        if(k==0)
        return nums;
        queue<char>st;
        string ans;
        int i=0,s=0;
        for(i=0;i<nums.length();i++){
            if(s<k){
            if(nums[i]==0){
                if(st.empty())
                continue;
                else
                st.push(nums[i]);
            }
            else{
                if(i<nums.length()-1&&nums[i]<nums[i+1])
                st.push(nums[i]);
                else
                s++;
            }
            }
            else
            break;
        }
        while(i<nums.length()){
            st.push(nums[i]);
            i++;
        }
        while(st.front()=='0')
        st.pop();
        while(!st.empty()){
            ans+=st.front();
            st.pop();
        }
        return ans;
    }
};
```
