**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    char findTheDifference(string s, string t) {
        int p1 = 0;
        for (const auto& ch : s) {
            p1 += ch;
        }

        int p2 = 0;
        for (const auto& ch : t) {
            p2 += ch;
        }

        return p2 - p1;
    }
};
```
**Explanation:**
	Цель: Даны две строки, в них одни и те же буквы, но во второй добавлен какой-то симовол. Нужно найти этот символ.
	Решение: Буквы это числа(по ASCII), значит сумма первого отличается от второго на один символ. Посчитать сумму первой строки и сумму второй строки. Вычесть из второй суммы первую - получится искомая буква.