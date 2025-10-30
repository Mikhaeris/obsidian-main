**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(3N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> leftRightDifference(vector<int>& nums) {
        int n = nums.size();

        vector<int> leftSum(n);
        leftSum[0] = 0;
        for (int i = 1; i < n; ++i) {
            leftSum[i] = leftSum[i-1] + nums[i-1];
        }

        vector<int> rightSum(n);
        for (int i = n-2; i >= 0; --i) {
            rightSum[i] = rightSum[i+1] + nums[i+1];
        }

        vector<int> answer(n);
        for (int i = 0; i < n; ++i) {
            answer[i] = abs(leftSum[i] - rightSum[i]);
        }

        return answer;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно вернуть массив сумма левых значений минус сумма правых.
	Решение: Получить левую сумму и правую сумму. Узнать разницу по модулю.