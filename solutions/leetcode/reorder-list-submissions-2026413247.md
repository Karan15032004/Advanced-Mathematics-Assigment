# reorder list/submissions/2026413247

**Platform:** LeetCode  
**Date:** 2026-06-08  

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
    ListNode* slastret(ListNode* head,ListNode* last){
        ListNode* slast=head;
        while(slast->next!=last)
        slast=slast->next;
        return slast;
    }
    ListNode* Middle(ListNode* head){
        ListNode* slow=head;
        ListNode* fast=head;
        while(fast!=NULL&&fast->next!=NULL){
            slow=slow->next;
            fast=fast->next->next;
        }
        return slow;
    }
    void reorderList(ListNode* head) {
        if(head->next==NULL||head->next->next==NULL)
        return ;
        ListNode* m=Middle(head);
        ListNode* temp=head;
        ListNode* last=head;
        while(last->next!=NULL)
        last=last->next;
        ListNode* slast=slastret(head,last);
        while(m->next!=NULL){
            slast->next=NULL;
            last->next=temp->next;
            temp->next=last;
            temp=temp->next->next;
            last=slast;
            slast=slastret(head,last);
        }
    }
};
```
