**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    ListNode* reverseBetween(ListNode* head, int left, int right) {
        ListNode* dummy = new ListNode(-1, head);
        ListNode* first_seg_tail = dummy;
        for (int i = 0; i < left-1; ++i) {
            first_seg_tail = head;
            head = head->next;
        }

        ListNode* mid_seg_head = NULL;
        ListNode* mid_seg_tail = head;
        for (int i = left; i <= right; ++i) {
            ListNode* tmp = head->next;
            head->next = mid_seg_head;
            mid_seg_head = head;
            head = tmp;
        }

        first_seg_tail->next = mid_seg_head;
        mid_seg_tail->next = head;

        return dummy->next;
    }
};
```
**Explanation:**
	Цель: Дан линкед лист и два индекса. Нужно перевернуть часть ликед листа начиная с левого идекса по правый, а остальные части оставить так же. Индексирование идеи от нуля.
	Pешение: Разделить на три части линкед лист, сделать dummy ноду и от нее сохранить начало и конце первой части. В центральной части перевернуть линкед лист как обычно, запомнив значение нового начала и конца. Дальше присоеденить первый сегмент - конце первого сегмента указывает на новое значение головы цетнра. Конец середины теперь должен указывать на оставшуюся часть. Вернуть значение dummy->next.