# insert interval/submissions/2030745582

**Platform:** LeetCode  
**Date:** 2026-06-12  

## Solution

```
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
        vector<vector<int>>ans;
        int start2=newInterval[0],end2=newInterval[1];int i=0,start1,end1;
        for(i=0;i<intervals[0].size();i++){
            start1=intervals[i][0];
            end1=intervals[i][1];
            if(end1>=start2){
                start1=start1;
                end1=max(end1,end2);
                break;
            }
            else if(end2>=start1){
                start1=start2;
                end1=max(end1,end2);
            }
            else{
                ans.push_back({start1,end1});
                start1=start2;
                end1=end2;
            }
        }
        if(i==intervals[0].size()-1)
        return intervals;
        i++;
        while(i<intervals[0].size()){
        start2=intervals[i][0];
        end2=intervals[i][1];
        if(end1>start2){
            start1=start1;
            end1=max(end1,end2);
        }
        else{
            ans.push_back({start1,end1});
            start1=start2;
            end1=max(end1,end2);
        }
        i++;
        }
        ans.push_back({start1,end1});
        return ans;
    }
};
```
