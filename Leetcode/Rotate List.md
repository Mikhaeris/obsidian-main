**Complexity:** Medium
Answer:
	Time Complexity: O(N+M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    ListNode* rotateRight(ListNode* head, int k) {
        if (head == NULL || head->next == NULL || k == 0) {
            return head;
        }

        int size = 1;
        ListNode* tail = head;
        while (tail->next != NULL) {
            tail = tail->next;
            ++size;
        }
        tail->next = head;
        tail = head;
        
        int pos = k % size;
        for (int i = 0; i < (size - pos - 1); ++i) {
            tail = tail->next;
        }
        head = tail->next;
        tail->next = NULL;
        return head;
    }
};
```
**Explanation:**
	Цель: Дан односвязный список. Нужно повернуть его вправо k раз.
	Pешение: Подсчитать количество элементов в списке и зациклить его. Дальше посчитать реальный поворот(т.е. сколько элементов нужно повернуть вправо). Теерь нужно узнать сколько на какой позиции окажется голова, оно равняется размер списка минут количество элемнтов которые надо повернуть. Пройтись до этго числа минус один. Назначить новую голову и разорвать список. Вернуть голову.