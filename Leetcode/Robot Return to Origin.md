**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool judgeCircle(string moves) {
        int x = 0, y = 0;

        for (const auto& ch : moves) {
            if (ch == 'U') {
                ++y;
            } else if (ch == 'D') {
                --y;
            } else if (ch == 'L') {
                --x;
            } else if (ch == 'R') {
                ++x;
            }
        }

        return (x == 0) && (y == 0);
    }
};
```
**Explanation:**
	Цель: Дан робот и строка его ходов. Нужно узнать вернутся ли он от туда, откуда начал. Взгляд не влияет.
	Pешение: Две переменные по двум осям. При движении смотреть какая ось и либо прибавлять, либо вычетать. Проверить что по обоим осям нуль.