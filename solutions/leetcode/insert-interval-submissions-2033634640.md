# insert interval/submissions/2033634640

**Platform:** LeetCode  
**Date:** 2026-06-15  

## Solution

```
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
        intervals.push_back(newInterval);
        sort(intervals.begin(),intervals.end());
        int start1=intervals[0][0];
        int end1=intervals[0][1];
        vector<vector<int>>ans;
        for(int i=1;i<intervals.size();i++){
            int start2=intervals[i][0];
            int end2=intervals[i][1];
            if(end1>=start2){
                start1=start1;
                end1=max(end2,end1);
                continue;
            }
            else{
                ans.push_back({start1,end1});
                start1=start2;
                end1=end2;
            }
        }
        ans.push_back({start1,end1});
        return ans;
        }
};
```
