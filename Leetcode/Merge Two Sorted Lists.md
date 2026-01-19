**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    ListNode* mergeTwoLists(ListNode* list1, ListNode* list2) {
        ListNode dummy(-101, NULL);
        ListNode* iter = &dummy;
        while (list1 != NULL && list2 != NULL) {
            if (list1->val <= list2->val) {
                iter->next = list1;
                list1 = list1->next;
            } else {
                iter->next = list2;
                list2 = list2->next;
            }
            iter = iter->next;
        }
        iter->next = (list1 != NULL) ? list1 : list2;
        return dummy.next;
    }
};
```
**Explanation:**
	Цель: Даны два отсортированных линкед листа. Нужно их объеденить.
	Pешение: Создать dummy голову и прикреплять к ней новые элементы. Проходится по обоим спискам и вставлять в новый лист меньший элемент. Так вставитяс один линкед лист, но еще может остаться какой-то хвост. Поэтому нужно к новому листу в конце добавить оставшийся хвост. Вернуть следующий элемент от dummy.