**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string longestCommonPrefix(vector<string>& strs) {
		for (int i = 0; i < strs[0].size(); ++i) {
			for (int j = 1; j < strs.size(); ++j) {
				if (strs[j][i] != strs[0][i]) {
					return strs[0].substr(0,i);
				}
			}
		}
		  
		return strs[0];
	}
};
```
**Explanation:**
	Цель: Нужно найти самый длинный прекси данных строк.
	Решение: Проходится по каждому символу каждого слова. Если символ не равен, то вернуть подстроку первой строки с нулевого по последний символ.