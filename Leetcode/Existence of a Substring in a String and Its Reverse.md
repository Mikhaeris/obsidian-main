**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	bool isSubstringPresent(string s) {
		for (int i = 0; i < s.size(); ++i) {
			for (int j = s.size() - 1; j > 0; --j) {
				if (s[i] == s[j] && s[i+1] == s[j-1]) {
					return true;
				}
			}
		}
		return false;
	}
};
```
**Explanation:**
	Цель: Проверить 
	Pешение: Пройтись по строке,собирая количество повторений всех символов. И параллельно ища максимальное колиечестов поторений для гласных и согласных букв. Вернуть их сумму.
