**Complexity:** Medium
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    void deleteNode(ListNode* node) {
        ListNode *next = node->next;
        node->val = next->val;
        node->next = next->next;
        delete next;
    }
};
```
**Explanation:**
	Цель: Дану узел односвязного списка. Нужно удалить этот узел, а так же сохранить целосность связного списка.
	Pешение: Чтобы удлаить данный, можно заменить его значение значением следующего и удалить следующий.