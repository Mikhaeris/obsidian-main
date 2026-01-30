**Complexity:** Hard  
Answer:  
- Time Complexity: O(N)
- Space Complexity: O(1)

Code:  
```cpp
class Solution {
public:
    ListNode* reverseKGroup(ListNode* head, int k) {
        ListNode dummy(-1, head);

        ListNode* iter = &dummy;
        while (haveNodes(head, k)) {
            ListNode* temp_head = NULL;
            ListNode* temp_tail = NULL;

            for (int i = 0; i < k; ++i) {
                ListNode* tmp = head->next;
                head->next = temp_head;
                temp_head = head;
                if (temp_tail == NULL) {
                    temp_tail = head;
                }
                head = tmp;
            }

            iter->next = temp_head;
            temp_tail->next = head;
            iter = temp_tail;
        }
       
        return dummy.next;
    }

    bool haveNodes(ListNode* iter, int k) {
        int counter = 0;
        while (iter != NULL && counter < k) {
            ++counter;
            iter = iter->next;
        }
        return counter == k;
    }
};
```
**Explanation:**
- Цель: Дан линкед лист, нужно в нем перевернуть ноды в группах по k.
- Pешение: Создать dummy ноду, от которой начать переворачивание, она нужна чтобы скреплять переворот и знать начало. Чтобы перевернуть ноды в группах по k нужно сначала узнать можно ли из первенуть. Поэтому с помощью специальной функции считать доступность переворота. Дальше переворачивать лист по обычному алгоритму, но в конце менять подвязку, итератор должен указывать на новую голову, а сам должен стать хвостом от текущего переворота.