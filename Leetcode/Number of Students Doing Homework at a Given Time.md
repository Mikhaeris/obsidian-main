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
	Цель: Дано время начала и конца обучение ученика. 
	Решение: сохранять в стеке скобки. Для каждой открытой должна быть закрытая.
	P.S. В таблице ASCII скобки '(' ')' стоят рядом, а '['  ']' и '{' '}' стоят через, поэтому не получится придумать какого0то короткого красивого алгоритма в две строчки кода :(