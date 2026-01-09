**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    ListNode* removeElements(ListNode* head, int val) {
        ListNode** pp = &head;
        while (*pp != NULL) {
            if ((*pp)->val == val) {
                ListNode* tmp = *pp;
                *pp = (*pp)->next;
                delete tmp;
            } else {
                pp = &((*pp)->next);
            }
        }
        return head;
    }
};
```
**Explanation:**
	Цель: Дан линдек лист. Нужно удалить в нем все ноды, в которых значение ноды равеняется данному.
	Pешение: Pointer-to-pointer техника, если текущее значение подходи, то можно удалять ноду - сохранить указательно на ноду, изменить значение поинтрена на поинтер на следующую ноду и удалить нужную ноду из памяти. Иначе просто перейти к следующей ноду.