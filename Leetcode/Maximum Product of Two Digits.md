**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxProduct(int n) {
        int f = 0, s = 0;
        while (n) {
            int num = n % 10;
            if (num > f) {
                s = f;
                f = num;
            } else if (num > s) {
                s = num;
            }
            n /= 10;
        }
        return f * s;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно найти максимальное произведение его двух цифр.
	Решение: С помощью остатка на 10 брать последюю цифру в числе и сохранять ее в двух максмиальных перменных. Делать число на десять. Повторять цикл, пока число больше нуля. Вернуть произведение двух смаых больгших найденных цифр.