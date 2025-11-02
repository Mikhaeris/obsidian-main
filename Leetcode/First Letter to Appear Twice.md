**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution1:
```cpp
class Solution {
public:
    char repeatedCharacter(string s) {
        char alph[26] = {0};
        for (const auto& ch : s) {
            if (++alph[ch-'a'] > 1) {
                return ch;
            }
        }
        return 0;
    }
};
```
**Explanation:**
	Цель: Найти первый символ, который повторяется два раза.
	Решение: В массиве сохранять количество повторений каждого символа, как только там будет два, вывести текущий символ.