**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int busyStudent(vector<int>& startTime, vector<int>& endTime, int queryTime) {
        int n = startTime.size();

        int count = 0;
        for (int i = 0; i < n; ++i) {
            if (startTime[i] <= queryTime && queryTime <= endTime[i]) {
                ++count;
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Дано время начала и конца обучение ученика. Дана точка во времени. Нужно узнать сколкьо учеников в это время училось.
	Решение: Линейно проверить, учился ли ученик в это время. Вернуть количество таких учеников.