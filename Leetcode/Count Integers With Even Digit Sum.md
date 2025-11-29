**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countEven(int num) {
        int count = 0;
        for (int i = 1; i <= num; ++i) {
            int sum = 0;
            int ci = i;
            while (ci) {
                sum += ci % 10;
                ci /= 10;
            }

            if (sum % 2 == 0) {
                ++count;
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно найти такие числа от 1 до этого числа, сумма цифр которых четная.
	Pешение: Проверять сумму цифр каждого числа и если сумма четная, то прибавлять счетчик. Вернуть количество цифр.