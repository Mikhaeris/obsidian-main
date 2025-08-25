**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isAcronym(vector<string>& words, string s) {
		if (words.size() != s.length()) {
			return false;
		}
		  
		for (int i = 0; i < s.length(); i++) {
			if (words[i][0] != s[i]) {
				return false;
			}
		}
		  
		return true;
	}
};
```
**Explanation:**
	Цель: Дан массив строк и строка. Нужно проверить что строка является акронимом к этому массиву строк.
	Решение: Проверить, что количество слов в масисве равняется количеству букв в слове. Проходится по первой букве в каждого слова в массиве и по каждой букве строки и проверять что они равны.