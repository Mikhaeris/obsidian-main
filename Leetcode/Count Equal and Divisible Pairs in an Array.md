**Complexity:** Easy
Answer:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int countPairs(vector<int>& nums, int k) {
        int n = nums.size();
        int count = 0;
        for (int i = 0; i < n; ++i) {
            for (int j = i+1; j < n; ++j) {
                if ((nums[i] == nums[j]) && ((i*j) % k == 0)) {
                    ++count;
                }
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно посчитать количество пар, которые соотвествуют условиям:  0<=i<j<n и i\*j делится без остатка на k.
	Pешение: Сделать то что сказано.