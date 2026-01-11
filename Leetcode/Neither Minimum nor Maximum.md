**Complexity:** Easy
Answer:
	Time Complexity: O(N\*log(N))
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int findNonMinOrMax(vector<int>& nums) {
        if (nums.size() < 3) {
            return -1;
        }

        sort(nums.begin(), nums.end());

        return nums[1];
    }
};
```
**Explanation:**
	Цель: Дан массив различных чисел. Нужно вернуть любое число, которое не является ни максимальным, ни минимальным.
	Pешение: Если в массиве меньше трех ждементов, то не подходит. Отсортировтаь массив и вернуть второй элемент.