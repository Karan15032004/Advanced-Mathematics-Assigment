# ipo/submissions/2068929142

**Platform:** LeetCode  
**Date:** 2026-07-15  

## Solution

```
class Solution {
public:
    int findMaximizedCapital(int k, int w, vector<int>& profits, vector<int>& capital) {
        int n=profits.size(),i=0;
        while(k>0){
            while(i<n){
                if(w>=capital[i]){
                    k--;
                    int temp1=profits[i];
                    while(i<n&&w>=capital[i])
                    temp1=max(temp1,profits[i++]);
                    w+=temp1;
                }
                else return w;
            }
        }
        return w;
        
    }
};
```
