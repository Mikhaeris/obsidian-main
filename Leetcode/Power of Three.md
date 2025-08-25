**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isPowerOfThree(int n) {
		if (n < 1) {
			return false;
		}
		  
		while (n % 3 == 0) {
			n /= 3;
		}
		  
		return n == 1;
	}
};
```
**Explanation:**
	Цель: Узнать, является ли число степенью тройки.
	Решение: Обычный подход, делить число пока нету остатка.

**Complexity:** Easy
Answer2:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isPowerOfThree(int n) {
		if (n < 1) {
			return false;
		}
		return !(1162261467 % n);
	}
};
```
**Explanation:**
	Цель: Узнать, является ли число степенью тройки.
	Решение: Это небольшой хак. Так как в числе только 32 бита, то максимаьным числом степени тройки является 1162261467. Применив законы алгебры, можно проверить делится ли это число на 3 - если взять большее число(которое точно делится на 3) и проверить остсток деления на данное число, то можно узнать является ли оно степенью тройки(если в кратце - все числа степени тройки кратны тройки следовательно они делятся друг на друга без остатка).