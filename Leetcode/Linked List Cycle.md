**Complexity:** Easy
Answer:
	Time Complexity: O(N)??
	Space Complexity: O(N)?
Code:
Solution:
```cpp
class Solution {
public:
    vector<ListNode*> all_nodes;
  
    inline bool inVecOfNodes(ListNode *node) {
        for (int i = 0; i < all_nodes.size(); ++i) {
            if (all_nodes[i] == node) {
                return true;
            }
        }
        return false;
    }
  
    bool hasCycle(ListNode *head) {
        while (head != nullptr) {
            if (inVecOfNodes(head->next)) {
                return true;
            }
            all_nodes.push_back(head);
            head = head->next;
        }
        return false;
    }
};
```
**Explanation:**
	Цель: Нужно узнать, есть ли в односвязанном листе цикл.
	[[Linked List]]
	Решение: Хранить все узлы в векторе, проверять есть ли этот узел в листе.

Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool hasCycle(ListNode *head) {
        ListNode* fast = head;
        ListNode* slow = head;
  
        while (fast != nullptr && fast->next != nullptr) {
            fast = fast->next->next;
            slow = slow->next;
  
            if (slow == fast) {
                return true;
            }
        }
  
        return false;
    }
};
```
**Explanation:**
	Цель: Нужно узнать, есть ли в односвязанном листе цикл.
	[[Linked List]]
	Решение: Два указателя, один бежит к следующему, другой через одного.
	Есть ли есть цикл, то в какой-то момент они обязательно встретятся.