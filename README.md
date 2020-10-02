# 206.-Reverse-Linked-List-Leet-Code-Problem-Solution-in-C++

    C++ Code:-
    
class Solution {
public:
    ListNode* reverseList(ListNode* head) {
        if(head==nullptr)
            return head;
        stack<ListNode*> s1;
        ListNode* temp;
        temp=head;
        while(temp!=nullptr){
            s1.push(temp);
            temp=temp->next;
        }
        temp=s1.top();
        head=temp;
        s1.pop();
        while(!s1.empty()){
            temp->next=s1.top();
            s1.pop();
            temp=temp->next;
        }
        temp->next=nullptr;
        temp=nullptr;
        free(temp);
        return head;
    }
};
