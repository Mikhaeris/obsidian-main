**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string generateTheString(int n) {
		return (n % 2) ? string(n, 'a') : string(n-1, 'a') + 'b';
	}
};
```
**Explanation:**
	Цель: Дано число, нужно вернуть такую строку что количество посторений каждого символа нечетное.
	Решение: Если число не четное, то можно вернуть строку из одного символа, иначе сделать строку из n-1 повторяющихся символов и в конце добавить другой символ.