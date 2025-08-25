**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minSubArrayLen(int target, vector<int>& nums) {
        int sum = nums[0];
        int min_size = INT_MAX;

        int l = 0, r = 0;
        while (l != nums.size()-1) {
            if (sum >= target) {
                min_size = min(r-l+1, min_size);
            }

            if ((sum < target || l == r) && r != nums.size()-1){
                sum += nums[++r];
            } else {
                sum -= nums[l++];
            }
        }

        if (sum >= target) {
            min_size = min(r-l+1, min_size);
        }
        return (min_size != INT_MAX) ? min_size : 0;
    }
};
```
**Explanation:**
	Цель: Нужно найти минимальную длину подмассива, в которой сумма чисел больше или равняется данному числу.
	Решение: С помощью двух указателей проходится по методу [[Sliding window]] по всему массиву, ищя данную сумму. Вернуть минимальную длину подмассива