**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> getConcatenation(vector<int>& nums) {
        int n = nums.size();
        vector<int> ans(2 * n);

        for (int i = 0; i < n; ++i) {
            ans[i] = ans[i + n] = nums[i];
            // ans[i] = nums[i % n];
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив, его надо удвоить(или сложить его два раза).
	Решение: Заполнять в новом массиве элементы либо по остатку от длиным массива, либо сразу два элеента.