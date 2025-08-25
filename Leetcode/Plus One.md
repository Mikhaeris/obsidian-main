**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> plusOne(vector<int>& digits) {
        for (int i = digits.size()-1; i >= 0; --i) {
            if (digits[i] < 9) {
                ++digits[i];
                return digits;
            }
            else {
                digits[i] = 0;
                if (i == 0) {
                    digits.insert(digits.begin(), 1);
                }
            }
        }
        
        return digits;
    }
};
```
**Explanation:**
	Цель: Есть длинное число, нужно добавить еденицу
	Решение: Пройтись по каждой цифре с конца.
	Если цифра равняется 9, то это цифра равняется 0, если это последний разряд, то добавить в самое начало новый разряд(цифру 1).
	Если цифра меньше 9, то прибавить к ней еденицу и вернуть длинное число.