**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
class Solution {
public:
	int alternateDigitSum(int n) {
		string str = to_string(n);
		int ans = 0;
		for (int i = 0; i < str.size(); ++i) {
			if (i & 1) {
				ans -= str[i] - '0';
			} else {
				ans += str[i] - '0';
			}
		}
		return ans;
	}
};
```
**Explanation:**
	Цель: Дано число, нужно сложить каждую цифру, чередую знак начиная с положительного.
	Pешение: Записать число в строку. Проходится от начла строки и прибавлять число учитывая знак. Вернуть ответ.
