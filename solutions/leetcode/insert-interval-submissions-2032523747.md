# insert interval/submissions/2032523747

**Platform:** LeetCode  
**Date:** 2026-06-14  

## Solution

```
class Solution {
public:
    vector<vector<int>> insert(vector<vector<int>>& intervals, vector<int>& newInterval) {
        vector<vector<int>>ans;
        sort(intervals.begin(),intervals.end());
        int start2=newInterval[0],end2=newInterval[1];int i=0,start1,end1;
        for(i=0;i<intervals.size();i++){
            start1=intervals[i][0];
            end1=intervals[i][1];
            if(end1>=start2){
                start1=start1;//3
                end1=max(end1,end2);//8
                break;
            }
            else{
                ans.push_back({start1,end1});
                continue;
            }
        }
        if(i==intervals.size()-1)
        return intervals;
        i++;
        while(i<intervals.size()){
        start2=intervals[i][0];
        end2=intervals[i][1];
        if(end1>=start2){
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
