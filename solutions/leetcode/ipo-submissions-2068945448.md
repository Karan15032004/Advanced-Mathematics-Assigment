# ipo/submissions/2068945448

**Platform:** LeetCode  
**Date:** 2026-07-15  

## Solution

```
class Solution {
public:
    int findMaximizedCapital(int k, int w, vector<int>& profits, vector<int>& capital) {
        vector<pair<int,int>>projects;
        for (int i = 0; i < capital.size(); i++) {
    projects.push_back({capital[i], profits[i]});
}
sort(projects.begin(), projects.end());
for (int i = 0; i < projects.size(); i++) {
    capital[i] = projects[i].first;
    profits[i] = projects[i].second;
}
        int n=profits.size(),i=0;
            while(i<n&&k>0){
                if(w>=capital[i]){
                    k--;
                    int temp1=profits[i];
                    while(i<n&&w>=capital[i])
                    temp1=max(temp1,profits[i++]);
                    w+=temp1;
                }
                else return w;
            }

        return w;
        
    }
};
```
