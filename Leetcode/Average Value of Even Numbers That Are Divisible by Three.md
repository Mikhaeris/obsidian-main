**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int averageValue(vector<int>& nums) {
        int sum = 0, count = 0;
        for (const auto& num : nums) {
            if (num % 2 == 0 & num % 3 == 0) {
                sum += num;
                ++count;
            }
        }
        return count ? sum / count : 0;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел, нужно посчитать среднее четных чисел, которые делятся на три.
	Решение: Проверять каждое число на делимость на два и на три. Если количество чисел равно нулю, то вернуть нуль, иначе вернять среднее значение.