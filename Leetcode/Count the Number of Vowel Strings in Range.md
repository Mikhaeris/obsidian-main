**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int vowelStrings(vector<string>& words, int left, int right) {
		int ans = 0;
		for (int i = left; i <= right; ++i) {
			char f = words[i][0];
			char l = words[i][words[i].length()-1];
			if ((f == 'a' || f == 'e' || f == 'i' || f == 'o' || f == 'u') &&
				(l == 'a' || l == 'e' || l == 'i' || l == 'o' || l == 'u')) {
				++ans;
			}
		}
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив слов. Нужно узнать сколько слов на отрезе от l до r начинаюся с главной и заканчиваются гласной.
	Решение: Проходится от l до r и проверять первыую и полсдежнюю букву слова.