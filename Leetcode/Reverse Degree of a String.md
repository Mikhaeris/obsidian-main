**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(?)
Code:
Solution:
```cpp
class Solution {
public:
	int reverseDegree(string s) {
		int sum = 0;
		for (int i = 0; i < s.length(); ++i) {
			sum += (26 - (s[i] - 'a')) * (i + 1);
		}
		return sum;
	}
};
```
**Explanation:**
	Цель: Дана строка, нужно узнать ее сумму последовательности(каждая буква в алфавите переворачивается и уножается на индекс и плюсуется к общей сумме).
	Pешение: Проходится по каждому элементу, смотреть его обратный числовой порядок, умножить на индекс и сложить с общей суммой. Вернуть сумму.