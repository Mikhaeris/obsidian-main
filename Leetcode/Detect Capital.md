**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    bool detectCapitalUse(string word) {
        int count_capital = 0;
        int count_not_capital = 0;

        for (const auto& ch : word) {
            if (isupper(ch)) {
                ++count_capital;
            } else {
                ++count_not_capital;
            }
        }

        int n = word.length();
        if ((count_capital == n) || (count_not_capital == n)) {
            return true;
        } else if (isupper(word[0]) && count_capital == 1) {
            return true;
        }

        return false;
    }
};
```
**Explanation:**
	Цель: Проверить что слово соостветсвует условию. Если все в верхнем регистре или все в нижнем регистре или только первая буква заглавная.
	Pешение: Просто проверить условия.