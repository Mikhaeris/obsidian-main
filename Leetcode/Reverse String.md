**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	void reverseString(vector<char>& s) {
		for (int l = 0, r = s.size()-1; l < r; l++, r--) {
#if 0
			char temp(move(s[l]));
			s[l] = move(s[r]);
			s[r] = move(temp);
#endif
			swap(s[l], s[r]);
		}
	}
};
```
**Explanation:**
	Цель: Дана строка,нужно ее перевернуть.
	Решение: Два указателя, менять местами.