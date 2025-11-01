**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    ListNode* modifiedList(vector<int>& nums, ListNode* head) {
        unordered_set<int> st(nums.begin(), nums.end());

        while (st.find(head->val) != st.end()) {
            head = head->next;
            if (head == nullptr) {
                return nullptr;
            }
        }

        ListNode* new_head = head;
        while (head && head->next) {
            if (st.find(head->next->val) != st.end()) {
                head->next = head->next->next;
            } else {
                head = head->next;
            }
        }
        return new_head;
    }
};
```
**Explanation:**
	Цель: Дан линкед лист и массив чисел(неповторяющихся). Нужно из линкед листа удалить все вхождения чисел из массива. Вернуть начало линкед листа.
	Решение: Заполнить хеш сет значениями и массива(для быстрой проверки нахождения числа в массиве). Сначала пропустить все ноды, где содержатся числа из массива. Дальше смотреть если в следующей ноде присутсвует значение из массива, тогда переназначить следующую ноду у текущей ноды на через следующую, иначе нода равняетс следующей.