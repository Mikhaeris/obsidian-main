**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int sumOfGoodNumbers(vector<int>& nums, int k) {
        int ans = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (i-k < 0) {
                if (nums[i] > nums[i+k]) {
                    ans += nums[i];
                }
            } else if (i+k < nums.size()) {
                if (nums[i] > nums[i+k] && nums[i] > nums[i-k]) {
                    ans += nums[i];
                }
            } else {
                if (nums[i] > nums[i-k]) {
                    ans += nums[i];
                }
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Узнать сумму хороших чисел. Хорошими числами считаются числа, которые строго больше чисел на позиция минус k и плюс k.
	Решение: Просто провреить каждый элемент и если он подходит, то добавлять в сумму.