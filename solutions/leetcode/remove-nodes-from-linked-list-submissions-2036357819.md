# remove nodes from linked list/submissions/2036357819

**Platform:** LeetCode  
**Date:** 2026-06-17  

## Solution

```
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
class Solution {
public:
    ListNode* removeNodes(ListNode* head){
    vector<int>arr,ans;
    while(head!=NULL) {
        arr.push_back(head->val);
        head=head->next;
    }
    stack<int>st;
    int n=arr.size();
    st.push(arr[n-1]);
    ans.push_back(arr[n-1]);
    for(int i=n-2;i>=0;i--){
        while(!st.empty()&&st.top()<=arr[i])
        st.pop();
        if(st.empty())
        ans.push_back(arr[i]);
        st.push(arr[i]);
    }
    reverse(ans.begin(),ans.end());
    ListNode* head1=new ListNode(ans[0]);
   // head1->val=ans[0];
    ListNode* temp=head1;
    for(int i=1;i<ans.size();i++){
        temp->next=new ListNode(ans[i]);
        temp=temp->next;
    }
    temp->next=NULL;
    return head1;
    }
};
```
