**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> getNoZeroIntegers(int n) {
		for (int i = 1; i < n; ++i) {
			if (!haveZero(i) && !haveZero(n-i)) {
				return {i, n-i};
			}
		}
		  
		return {-1, -1};
	}
	  
private:
	bool haveZero(int n) {
		if (n == 0) {
			return true;
		}
		while (n) {
			if (n % 10 == 0) {
				return true;
			}
			n /= 10;
		}
		  
		return false;
	}
};
```
**Explanation:**
	Цель: Дано число. Нужно вернуть два числа, сумма которых равна данному и оба чиса не должны содержать нулей.
	Решение: Пройтись по всем числам от 1 до n. Для каждого i проверять, что i не содержит нулей и n-i не содержит нулей.
