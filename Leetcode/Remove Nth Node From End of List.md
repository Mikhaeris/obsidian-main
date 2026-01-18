**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        ListNode dummy(-1, head);
        
        ListNode* slow = &dummy;
        ListNode* fast = &dummy;
        for (int i = 0; i <= n; ++i) {
            fast = fast->next;
        }
        
        while (fast != NULL) {
            slow = slow->next;
            fast = fast->next;
        }

        ListNode* tmp = slow->next;
        slow->next = slow->next->next;
        delete tmp;

        return dummy.next;
    }
};
```
**Explanation:**
	Цель: Дан линкед лист. Нужно удалить n-ю ноду с конца.
	Pешение: Техника двух указателей и пустой головы(для ситуации когда удаляется первая нода). Быстрый идет вперед на n нод, следовательно медленный будет указывать на следующую ноду, которую надо удалить. Пройтись по всему линкед листу до конца и удалить нужную ноду.