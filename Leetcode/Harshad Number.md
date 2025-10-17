**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int sumOfTheDigitsOfHarshadNumber(int x) {
        int cx = x;
        int sum = 0;

        while (cx) {
            sum += cx % 10;
            cx /= 10;
        }

        return (x % sum == 0) ? sum : -1;
    }
};
```
**Explanation:**
	Цель: Узнать делится ли число на сумму цифр в нем.
	Pешение: Посчиать сумму числа и узнать делится ли оно без остатка.