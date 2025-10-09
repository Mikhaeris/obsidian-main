**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int addDigits(int num) {
        while (num / 10 > 0) {
            int temp = 0;
            while (num) {
                temp += num % 10;
                num /= 10;
            }
            num = temp;
        }
        
        return num;
    }
};
```
**Explanation:**
	Цель: Узнать какое число получится, после поучения суммы цифр в числе, пока не станет одна цифра в числе.
	Pешение: Пока исходно число больше 9, скадывать его цифры, исходное число приравнять к полученной сумме. 