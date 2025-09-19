**Complexity:** Easy
Answer:
	Time Complexity: O(N+M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string firstPalindrome(vector<string>& words) {
		for (const auto& word : words) {
			bool flag = true;
			int l = 0, r = word.length() - 1;
			while (l < r) {
				if (word[l] != word[r]) {
					flag = false;
				}
				++l;
				--r;
			}
			if (flag) {
				return word;
			}
		}
		return "";
	}
};
```
**Explanation:**
	Цель: Найти первое слово, являющееся палиндромом.
	Pешение: Проходится и проверять каждое слово на то, является ли оно палиндромом.