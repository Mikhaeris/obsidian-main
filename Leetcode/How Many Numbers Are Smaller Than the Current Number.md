**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> smallerNumbersThanCurrent(vector<int>& nums) {
        int n = nums.size();
        vector<int> ans(n, 0);
        for (int i = 0; i < n; ++i) {
            for (int j = 0; j < n; ++j) {
                if (i == j) {
                    continue;
                }

                if (nums[i] > nums[j]) {
                    ++ans[i];
                }
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Узнать скольок чисел, меньше чем данное число.
	Решение: Просто проверять и считать.