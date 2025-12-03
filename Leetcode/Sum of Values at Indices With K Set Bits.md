**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int sumIndicesWithKSetBits(vector<int>& nums, int k) {
        int n = nums.size();

        int ans = 0;
        for (int i = 0; i < n; ++i) {
            int count = 0;
            int cn = i;
            while (cn) {
                cn &= cn - 1;
                ++count;
            }
            if (count == k) {
                ans += nums[i];
            }
        }
        
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел и число. Нужно найти сумму чисел, индексы которых содержат только даное количество битов.
	Решение: Проходится по каждому индексу и проверять сколько в нем битов. Если количество битов равно числу, то прибавить к сумму. Вернуть сумму.