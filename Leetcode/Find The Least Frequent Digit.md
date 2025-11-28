**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int getLeastFrequentDigit(int n) {
        unordered_map<int, int> mp;
        while (n) {
            ++mp[n%10];
            n /= 10;
        }

        int m = INT_MAX, c = INT_MAX;
        for (const auto& pr : mp) {
            if (pr.second < c) {
                m = pr.first;
                c = pr.second;
            } else if (pr.second == c && pr.first < m) {
                m = pr.first;
                c = pr.second;
            }
        }
        return m;
    }
};
```
**Explanation:**
	Цель: Дано число. Нужно найти в нем такую цифру, в которая, повторяется меньше всего раз, если таких цифр несколько вернуть минимальную.
	Решение: Сохранить повторение каждой цифры в хеш таблице и найти в ней наимньшее повторяющееся. Вернуть такое число.