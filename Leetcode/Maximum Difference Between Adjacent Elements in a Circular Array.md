**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxAdjacentDistance(vector<int>& nums) {
        int max_diff = abs(nums[0] - nums[nums.size()-1]);
        for (int i = 1; i < nums.size(); ++i) {
            if (max_diff < abs(nums[i-1] - nums[i])) {
                max_diff = abs(nums[i-1] - nums[i]);
            }
        }
  
        return max_diff;
    }
};
```
**Explanation:**
	Цель: Найти максимальную разницу между соседними элементами в массиве по модулю, так же массив зациклен(т.е. первый и последний элемент соседи).
	Решение: В переменной сохранить результат разницы между первый и последни мэлементом по модулю. Дальше проходится по всем элементам и сранвивать текущую и максимальную разницу по модулю и перезаписывать при неаобходимости.