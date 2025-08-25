**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {  
	    ListNode* dummy = new ListNode();  
	    ListNode* l = dummy;  
	    int carry = 0;  
	    while (l1 != nullptr || l2 != nullptr || carry) {  
	        ListNode* newNode = nullptr;  
	        if (l1 != nullptr && l2 != nullptr) {  
	            int sum = l1->val + l2->val;  
	            if (carry) {  
	                sum++;  
	                carry--;  
	            }  
	            newNode = sum > 9 ? new ListNode(sum % 10) : new ListNode(sum);  
	            carry += sum / 10;  
	            l1 = l1->next;  
	            l2 = l2->next;  
	        }  
	        else if (l1 == nullptr && l2 != nullptr) {  
	            if (carry && l2->val == 9) {  
	                newNode = new ListNode();  
	            }  
	            else if (carry) {  
	                newNode = new ListNode(l2->val + carry);  
	                carry--;  
	            }  
	            else {  
	                newNode = new ListNode(l2->val);  
	            }  
	            l2 = l2->next;  
	        }  
	        else if (l2 == nullptr && l1 != nullptr) {  
	            if (carry && l1->val == 9) {  
	                newNode = new ListNode();  
	            }  
	            else if (carry) {  
	                newNode = new ListNode(l1->val + carry);  
	                carry--;  
	            }  
	            else {  
	                newNode = new ListNode(l1->val);  
	            }  
	            l1 = l1->next;  
	        }  
	        else {  
	            newNode = new ListNode(carry);  
	            carry--;  
	        }  
	        l->next = newNode;  
	        l = l->next;  
	    }  
	    return dummy->next;  
	}
};
```
**Explanation:**
	Цель: Даны два односвязных списка со значениями, нужно получить список из суммы этих нод.
	Решение: Первая реализация кода.

Answer2:
	Time Complexity: O(N*\N*\log(N))
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {  
	    ListNode dummy;  
	    ListNode* tail = &dummy;  
	    int carry = 0;  
	    while (l1 || l2 || carry) {  
	        int sum = carry;  
	        if (l1) {  
	            sum += l1->val;  
	            l1 = l1->next;  
	        }  
	        if (l2) {  
	            sum += l2->val;  
	            l2 = l2->next;  
	        }  
	  
	        carry = sum / 10;  
	  
	        tail->next = new ListNode(sum % 10);  
	        tail = tail->next;  
	    }  
	  
	    return dummy.next;  
	}
};
```
**Explanation:**
	Цель: Узнать есть ли дупликаты в векторе.
	Решение: Рефакторинг и оптимизация. Код чище и понятнее. В этом коде исключена утечка памяти.
	По сути каждый раз складываются узлы(если они есть) и прибавляется остаток(с прошлой итерации). Остаток равняется деление 10 на сумму(с этой итерации). Следующий узел равняется остаток от суммы.

Minimum line of code:
```cpp
class Solution {
public:
	ListNode* addTwoNumbers(ListNode* l1, ListNode* l2) {  
	    ListNode dummy;  
	    ListNode* tail = &dummy;  
	    int carry = 0;  
	    while (l1 || l2 || carry) {  
	        int sum = carry + (l1 ? l1->val : 0) + (l2 ? l2->val : 0); 
	  
	        carry = sum / 10;  
	  
	        tail->next = new ListNode(sum % 10);  
	        tail = tail->next;

			if (l1) {  l1 = l1->next;  }  
	        if (l2) {  l2 = l2->next;  }  
	    }  
	  
	    return dummy.next;  
	}
};
```