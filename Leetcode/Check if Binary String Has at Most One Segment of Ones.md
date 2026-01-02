**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool checkOnesSegment(string s) {
        for (int i = 1; i < s.size(); ++i) {
            if ((s[i-1] == '0') && (s[i] == '1')) {
                return false;
            }
        }
        return true;
    }
};
```
**Explanation:**
	Цель: Дана строка из нулей и едениц. Нужно убедится, что в ней есть только одна подстрока из едениц. Лидируюших нулей нет.
	Pешение: Получается нужно найти только начало следующей последовательности и вернуь false. Так как если нет лидирующих нулей, значит строка начинается из едениц.
