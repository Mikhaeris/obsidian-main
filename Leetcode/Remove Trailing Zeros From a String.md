**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    string removeTrailingZeros(string num) {
        int count = 0;
        for (int i = num.size()-1; i >= 0; i--) {
            if (num[i] == '0') {
                count++;
            } else {
                break;
            }
        }
        num.resize(num.size() - count);
        return num;
    }
};
```
**Explanation:**
	Цель: Дана строка, нужно удалить завершающие нули.
	Pешение: Просто подсчитать количество заверешающих нулей и изменить размер строки.