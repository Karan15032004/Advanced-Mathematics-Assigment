# squares of a sorted array/submissions/2020201907

**Platform:** LeetCode  
**Date:** 2026-06-02  

## Solution

```
class Solution {
public:
    vector<int> sortedSquares(vector<int>& nums) {
        int n=nums.size();
        vector<int> pos,neg,ans;
        for(int i=0;i<n;i++){
            if(nums[i]>=0)
            pos.push_back(nums[i]);
            else if(nums[i]<0)
            neg.push_back(nums[i]);
        }
        if(pos.size()==0){
            for(int i=0;i<neg.size();i++)
            neg[i]*=neg[i];
            reverse(neg.begin(),neg.end());
            return neg;
        }
         if(neg.size()==0){
            for(int i=0;i<pos.size();i++)
            pos[i]*=pos[i];
            return pos;
        }
        for(int i=0;i<pos.size();i++)
        pos[i]*=pos[i];
        for(int i=0;i<neg.size();i++)
        neg[i]*=neg[i];
        reverse(neg.begin(),neg.end());
        int i=0,j=0;
        while(i<pos.size()&&j<neg.size()){
            if(pos[i]<neg[j]){
            ans.push_back(pos[i]);
            i++;
            }
            else{
            ans.push_back(neg[j]);
            j++;}
        }
        while(i<pos.size())
        ans.push_back(pos[i++]);
        while(j<neg.size())
        ans.push_back(neg[j++]);
        return ans;
    }
};
```
