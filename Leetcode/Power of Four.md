**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isPowerOfFour(int n) {
		if (n < 1) {
			return false;
		}
		  
		while (n % 4 == 0) {
			n /= 4;
		}
		  
		return n == 1;
	}
};
```
**Explanation:**
	Цель: Проверить является ли число степению четверки.
	Решение: Делить пока получается. Остаток должен быть 1, иначе число не является степенью четырех.