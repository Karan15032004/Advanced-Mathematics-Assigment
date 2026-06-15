# 🔥 Time Complexity

**Platform:** GeeksForGeeks  
**Date:** 2026-06-15  

## Solution

```
class Solution {
  public:
    int minMeetingRooms(vector<int> &start, vector<int> &end) {
        // code here
        int n=start.size();
        int i=0,rooms=0,j=0;
        sort(start.begin(),start.end());
        sort(end.begin(),end.end());
        while(i<n){
            if(start[i]<end[j]){
                rooms++;
                i++;
            }
            else{
                rooms--;
                j++;
            }
        }
        return rooms;
    }
};

```
