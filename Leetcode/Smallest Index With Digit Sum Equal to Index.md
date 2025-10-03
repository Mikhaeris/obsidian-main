**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution1:
```cpp
class Solution {
public:
    int smallestIndex(vector<int>& nums) {
        for (int i = 0; i < nums.size(); ++i) {
            int sum = 0;
            do {
                sum += nums[i] % 10;
            } while (nums[i] /= 10);

            if (i == sum)
                return i;
        }
        return -1;
    }
};
```
**Explanation:**
	Цель: Вернуть минимиальный индекс, так что сумма цифр этого элемента равняется этому индексу.
	Решение: Находить сумму числа и сравнивтаь ее с индесом.