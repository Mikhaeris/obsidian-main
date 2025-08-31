**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int countDigits(int num) {
		int count = 0;
		int cnum = num;
		do {
			if ((num % (cnum % 10)) == 0)
				++count;
		} while (cnum /= 10);
		return count;
	}
};
```
**Explanation:**
	Цель: Узнать сколько цифр из числа позволяют делаить данное число без остатка.
	Решение: Проходится по каждой цифре и проверять.