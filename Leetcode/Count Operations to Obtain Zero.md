**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countOperations(int num1, int num2) {
        int count = 0;
        while (num1 != 0 && num2 != 0) {
            if (num1 >= num2) {
                num1 -= num2;
            } else {
                num2 -= num1;
            }
            ++count;
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дано два числа, нужно узнать сколько операций потребуется чтобы преврить хотя бы одно число в нуль. Если первое число больше второго, то из первого вычесть второе, иначе наоброт.
	Решение: Выволнять операции, пока число не станет равным нулю и вернуть количество таких операций.