**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string reverseWords(string s) {
		int l = 0, r = 0;
		while (l < s.size()) {
			if (s[l] != ' ') {
				if (s[r+1] == ' ' || s[r+1] == '\0') {
					if (l == r) {
						++l;
						++r;
						continue;
					}
					  
					int t = r+1;
					while (l < r) {
						int temp = s[l];
						s[l++] = s[r];
						s[r--] = temp;
					}
					l = r = t;
				}
				++r;
			} else {
				++l;
			}
		}
		  
		return s;
	}
};
```
**Explanation:**
	Цель: Перевернуть все слова в строке.
	Решение: Самое некрасивое решение, которое только возможно, но по другому не написать.
	Проходится двумя указателя в поисках слова, когда слово найдено - переворачивать его и двигать указатели на конце слова плюс один. Повторять пока l не дойдет до конца.