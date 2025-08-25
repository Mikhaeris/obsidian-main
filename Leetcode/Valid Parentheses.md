**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isValid(string s) {
	    stack<char> sk;
	    for (const auto& ch : s) {
	        if (ch == '(' || ch == '[' || ch == '{') {
	            sk.push(ch);
	        }
	        else {
	            if (sk.empty()) {
	                return false;
	            }
	            if (ch == ')' && sk.top() == '(' ||
	                ch == ']' && sk.top() == '[' ||
	                ch == '}' && sk.top() == '{') {
	                sk.pop();
	            } else {
	                return false; 
	            }
	        }
	    }
	
	    return sk.empty();
	}
};
```
**Explanation:**
	Цель: Проверить скобочную последовательность.
	Решение: сохранять в стеке скобки. Для каждой открытой должна быть закрытая.
	P.S. В таблице ASCII скобки '(' ')' стоят рядом, а '['  ']' и '{' '}' стоят через, поэтому не получится придумать какого0то короткого красивого алгоритма в две строчки кода :(