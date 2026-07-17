# ipo/submissions/2070988431

**Platform:** LeetCode  
**Date:** 2026-07-17  

## Solution

```
class Solution {
public:
    int findMaximizedCapital(int k, int w, vector<int>& profits, vector<int>& capital) {
        int n=capital.size();
        vector<pair<int,int>>projects;
        for (int i = 0; i < capital.size(); i++) {
    projects.push_back({capital[i], profits[i]});
}
int idx=0;
sort(projects.begin(), projects.end());
priority_queue<int>pq;
while(k--){
while(idx<n&&w>=projects[idx].first){
pq.push(projects[idx].second);
idx++;
}
if(pq.empty())
return w;
w+=pq.top();
pq.pop();
}
  return w;      
    }
};
```
