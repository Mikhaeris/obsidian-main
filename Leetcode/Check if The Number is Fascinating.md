**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	bool isFascinating(int n) {
		int num[10];
		for (int i = 1; i <= 3; i++) {
			int cn = n*i;
			do {
				if (++num[cn % 10] > 1 || num[0] != 0) {
					return false;
				}
			} while (cn/=10);
		}
		  
		return true;
	}
};
```
**Explanation:**
	Цель: Дано число. Нужно проверить великолепное ли оно. Число считается великолепным, если после конкатенации n + n\*2 + n\*3 в числе ровно один раз повторяетс каждая цифра и нет нулей.
	Решение: Проходтся по чисалм от n до n\*3 и в каждом таком числе считать колиество повторений и если цифра повторяется больше одного раза или втретился ноль, то число можно считать не великолепным, иначе оно великолепное.