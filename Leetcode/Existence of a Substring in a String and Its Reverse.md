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
	Цель: Проверить есть ли строке такие подстроки длинной 2, что они повторяются в этой же перевернутой строке.
	Pешение: Проходится от начала строки, ища с конца такой же символ и проверя что следующий символы тоже равны - вернуть что есть, иначе что нет.
	P.S. Вероятно брутфорс это единственное решение. Это решение с оптимизацией по памяти, так как не создается копия этой строки. А проверятется все на месте.
