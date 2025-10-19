**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int mostFrequent(vector<int>& nums, int key) {
        unordered_map<int, int> mp;
        int max_n = 0, max_count = 0;
        for (int i = 0; i < nums.size()-1; ++i) {
            if (nums[i] == key) {
                if (++mp[nums[i+1]] > max_count) {
                    max_n = nums[i+1];
                    max_count = mp[nums[i+1]];
                }
            }
        }
        return max_n;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел и ключ. Нужно узнать какое число чаще встречается в массиве после ключа.
	Решение: В хэш таблице хранить число и количество его повторений. Вывести число, которые встречается чаще всего.