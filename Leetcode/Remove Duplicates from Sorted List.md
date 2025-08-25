**Complexity:** Easy
**Task:**
	En: Given the `head` of a sorted linked list, _delete all duplicates such that each element appears only once_. Return _the linked list **sorted** as well_.
	Ru: Дано указатель на голову отсортированного связного списка. Удалите все дубликаты так, чтобы каждый элемент встречался только один раз. Верните также отсортированный связный список.
	
**Example:**
	**Example 1:**
	![](https://assets.leetcode.com/uploads/2021/01/04/list1.jpg)
	**Input:** head = [1,1,2]
	**Output:** [1,2]

**Example 2:**
	![](https://assets.leetcode.com/uploads/2021/01/04/list2.jpg)
	**Input:** head = [1,1,2,3,3]
	**Output:** [1,2,3]

**Constraints:**
	`1 <= words.length <= 50`
	`1 <= words[i].length <= 50`
	`x` is a lowercase English letter.
	`words[i]` consists only of lowercase English letters.
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode() : val(0), next(nullptr) {}
 *     ListNode(int x) : val(x), next(nullptr) {}
 *     ListNode(int x, ListNode *next) : val(x), next(next) {}
 * };
 */
    ListNode* deleteDuplicates(ListNode* head) {
        if (!head) {
            return head;
        }
        ListNode* start = head;
        while (head->next) {
            if (head->val == (head->next)->val) {
                head->next = (head->next)->next;
            }
            else {
                head = head->next;
            }
        }
        return start;
    }
};
```
**Explanation:**
	Цель: Убрать все дубликаты в сортированном односвязном списке.
	Решение: Проходится по каждому элементу. Если значение этого элемента равняется значению следующего, то просто поменять указатель этого элемента на следующий следующего. Если значения не равно, то переходить к следующему элементу.