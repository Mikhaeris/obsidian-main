**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<double> convertTemperature(double& celsius) {  
		return {{celsius+273.15}, {(celsius * 1.8) + 32}};  
	}
};
```
**Explanation:**
	Цель: Перевести температуру из Цельсии в Кельвины и в Фаренгейты.
	Решение: Просто первести и вернуть.