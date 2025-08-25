**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int lengthOfLastWord(string s) {
		int length = 0;
		for (int i = s.size()-1; i >= 0; --i) {
			if (length != 0 && s[i] == ' ') {
				return length;
			}
			if (s[i] != ' ') {
				++length;
			}
		}
		  
		return length;
	}
};
```
**Explanation:**
	Цель: Дана строка, нужно вернуть длину последнего слова.
	Решение: Начинать с конца, пропустить первые пробелы, потом будет подсчет слова и дальше если встретится пробел - значит слово закончилось и вернуть длину. Если слово короткое и условие выхода не сработает, то в конце для этого случая возвразается собранная длина.
