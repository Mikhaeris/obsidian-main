**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> findErrorNums(vector<int>& nums) {
        int n = nums.size();
        sort(nums.begin(), nums.end());

        int sum = 0, dupl = 0;
        for (int i = 0; i < n; ++i) {
            if (i+1 < n && nums[i] == nums[i+1]) {
                dupl = nums[i];
            }
            sum += nums[i];
        }

        int expected = n * (n + 1) / 2;
        int missing = expected - (sum - dupl);

        return {dupl, missing};
    }
};
```
**Explanation:**
	Цель: Дан массив чисел, в нем продублировано одно чсло. Нужно узнать что за число продублировано и какой число пропущено.
	Решение: Отсортиовать массив. Посчитать сумму и найти дублирующийся элемент. Вернуть дублирующ