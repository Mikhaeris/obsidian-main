
**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution1:
```cpp
class Solution {
public:
    vector<int> getSneakyNumbers(vector<int>& nums) {
        vector<int> ans;
        unordered_map<int, int> mp;
        for (const auto& num : nums) {
            if (++mp[num] > 1) {
                ans.push_back(num);
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно найти два таких числа, котрые повторяются в массиве два раза.
	Решение: В хэш таблице хранить число и количество его повторений. Если количество повторений больше одного, то добавить в массив. Вернуть массив.

Answer:
	Time Complexity: O(N)
	Space Complexity: O(3N)
Code:
Solution2:
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