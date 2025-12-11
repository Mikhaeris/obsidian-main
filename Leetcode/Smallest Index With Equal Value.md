**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int smallestEqual(vector<int>& nums) {
        int n = nums.size();
        for (int i = 0; i < n; ++i) {
            if (i % 10 == nums[i]) {
                return i;
            }
        }
        return -1;
    }
};
```
**Explanation:**
	Цель: Нужно вернуть индекс наименьшего индекса, который (i mod 10 == nums\[i])
	Решение: Проверять каждый индекс и если индекс подходит, то возвращать этот индекс.