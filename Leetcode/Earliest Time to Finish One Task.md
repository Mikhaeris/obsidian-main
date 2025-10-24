**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int earliestTime(vector<vector<int>>& tasks) {
        int t_min = tasks[0][0] + tasks[0][1];
        for (const auto& t : tasks) {
            t_min = min(t_min, t[0] + t[1]);
        }
        return t_min;
    }
};
```
**Explanation:**
	Цель: Даны задачи - время начала и продолжительность. Узнать какая задача заверишится первой.
	Решение: Подсчитать.