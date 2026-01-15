**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode dummy(0, head);
        
        ListNode* cur = &dummy;
        while (cur->next != NULL && cur->next->next != NULL) {
            if (cur->next->val == cur->next->next->val) {
                int x = cur->next->val;
                while (cur->next != NULL && cur->next->val == x) {
                    ListNode* tmp = cur->next;
                    cur->next = cur->next->next;
                    delete tmp;
                }
            } else {
                cur = cur->next;
            }
        }
        return dummy.next;
    }
};
```
**Explanation:**
	Цель: Дан линкед лист. Нужно удалить все дубликаты.
	Pешение: Проходится по диндке листу от dummy, проверяя что следующий равен следующему. Тогда удалять следующий и менять указатель текущего на следующий следующего.

Code2:
```cpp
class Solution {
public:
    ListNode* deleteDuplicates(ListNode* head) {
        ListNode dummy(0, head);
        
        ListNode** pp = &dummy.next;
        while (*pp != NULL && (*pp)->next != NULL) {
            if ((*pp)->val == (*pp)->next->val) {
                int x = (*pp)->val;
                while (*pp != NULL && (*pp)->val == x) {
                    ListNode* tmp = *pp;
                    *pp = (*pp)->next;
                    delete tmp;
                }
            } else {
                pp = &((*pp)->next);
            }
        }
        return dummy.next;
    }
};
```
**Explanation:**
	Тоже самое решение, только с помощью pointer-to-pointer.