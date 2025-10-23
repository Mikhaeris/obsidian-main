**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    bool hasSameDigits(string s) {
        string temp = s;
        while (temp.length() > 2) {
            temp = "";
            for (int i = 1; i < s.length(); ++i) {
                temp += (((s[i-1] - '0') + (s[i] - '0')) % 10) + '0';
            }
            s = temp;
        }
        return (temp[0] == temp[1]) ? true : false;
    }
};
```
**Explanation:**
	Цель: Дано число, каждую итерацию формируется новая строка из суммы двух соседних цифр и берется модуль по 10, пока длина строки не станет равной двум. Проверить равны ли две оставшиеся цифры.
	Pешение: Совершать данные операции пока длина не станет равной двум. И проверить равны ли два оставшихся цифры на равенство.