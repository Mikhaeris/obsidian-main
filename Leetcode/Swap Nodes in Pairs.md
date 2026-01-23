**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    ListNode* swapPairs(ListNode* head) {
        if (head == NULL || head->next == NULL) {
            return head;
        }

        ListNode dummy(-1, head);
        ListNode* iter = &dummy;
        while (iter->next != NULL && iter->next->next != NULL) {
            ListNode* first = iter->next;
            ListNode* second = iter->next->next;

            iter->next = second;
            first->next = second->next;
            second->next = first;

            iter = iter->next->next;
        }

        return dummy.next;
    }
};
```
**Explanation:**
	Цель: Дан линкед лист. Нужно поменять ноды по парам.
	Pешение: От dummy ноды проходится и менять следующие две ноды между собой, пока существует следующая и следующая за ней.