**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int xorOperation(int n, int start) {
		int arr_xor = start;
		while (--n) {
			arr_xor ^= (start += 2);
		}
		return arr_xor;
	}
};
```
**Explanation:**
	Цель: Дано число откуда начинается последовательность и количество чисел в этой послежовательности. Нужно XOR этой подполседовательности.
	Решение: N раз совершать оперцию над каждым числом последовательности. Вернуть получившееся число.