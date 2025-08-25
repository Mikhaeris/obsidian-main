**Complexity:** Easy
Answer1:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximumDifference(vector<int>& nums) {
        int max_num = 0;
        for (int i = 0; i < nums.size(); ++i) {
            for (int j = i; j < nums.size(); ++j) {
                if (max_num < nums[j] - nums[i]) {
                    max_num = nums[j] - nums[i];
                }
            }
        }

        if (max_num == 0) {
            return -1;
        }
        return max_num;
    }
};
```
**Explanation:**
	Цель: Надо найти максимальную разницу между двями числами в массиве, такими что i < j.
	Решение: Перебор всех возможных варинтов. Минимальная оптимизация j = i.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximumDifference(vector<int>& nums) {
        int max_diff = -1;
        int min_num = nums[0];

        for (int i = 1; i < nums.size(); ++i) {
            if (nums[i] > min_num) {
                max_diff = max(nums[i] - min_num, max_diff);
            }

            if (nums[i] < min_num) {
                min_num = nums[i];
            }
        }

        return max_diff;
    }
};
```
**Explanation:**
	Цель: Надо найти максимальную разницу между двями числами в массиве, такими что i < j.
	Решение: Так как i < j, тогда можно как бы сделать два указателя(но только хранить предыдущее число). Т.е. сохранять минимальное число и вычислять с текущим минимальным. Проходится по каждому числу, если это число больше минимального, тогда брать максимальное число между текущим минус минимальное и текущей максимальной разницой. Если текущее число меньше минимального, тогда минимальное становится этим.