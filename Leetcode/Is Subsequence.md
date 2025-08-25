**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool isSubsequence(string s, string t) {
	    int ptr_s = 0;
	    for (int ptr_t = 0; ptr_t < t.size() && ptr_s < s.size(); ++ptr_t) {
	        if (s[ptr_s] == t[ptr_t]) {
	            ++ptr_s;
	        }
	    }
	
	    return ptr_s == s.size();
	}
};
```
**Explanation:**
	Цель: Проверить содержится ли строка s в строке t, пропуская любое количество символов.
	Решение: Два указател. Один в s, другой в t. Проходится по каждому символу по строке t. Если указатель s и в t указывают на один и тот же символ, то указатель s двигается вправо.
	Если указатель s равняется размеру строки s, то true, иначе false.