**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool checkDivisibility(int n) {
        int cn = n;
        int f = 0, s = 1;

        while (cn) {
            f += cn % 10;
            s *= cn % 10;
            cn /= 10;
        }

        return n % (f + s) == 0;
    }
};
```
**Explanation:**
	Цель: Нужно узнать делится ли число на сумму его цифр плюс сумма его произведений.
	Решение: Получить сумму цифр и сумму его произведений. Сложить их и проверить делиьтся ли число на полученное число.