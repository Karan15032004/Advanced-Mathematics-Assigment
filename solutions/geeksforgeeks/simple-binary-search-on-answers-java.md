# Simple Binary Search on Answers! - Java

**Platform:** GeeksForGeeks  
**Date:** 2026-06-23  

## Solution

```
class Solution {
  public:
    bool helper(vector<int>stalls,int guess,int k){
        int cows=1,lastpos=stalls[0];
        for(int i=1;i<stalls.size();i++){
            int diff=stalls[i]-lastpos;
            if(diff>=guess)
            {
                cows++;
                lastpos=stalls[i];
            }
            else
            continue;
        }
        if(cows>=k)
        return true;
        else
        return false;
    }
    int aggressiveCows(vector<int> &stalls, int k) {
        // code here
        sort(stalls.begin(),stalls.end());
        int low=1,n=stalls.size(),high=stalls[n-1],guess=1,res=1;
        while(low<=high){
            guess=low+(high-low)/2;
            if(helper(stalls,guess,k)){
                res=guess;
                low=guess+1;
            }

            else
            high=guess-1;
        }
        return res;
    }
};

```
