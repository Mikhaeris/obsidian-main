**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution1:
```cpp
class Solution {
public:
    int maxScore(string s) {
        int sum = 0;
        for (int i = 0; i < s.size(); ++i) {
            if (s[i] == '1') ++sum;
        }

        int max_sum = 0;
        for (int i = 0; i < s.size()-1; ++i) {
            if (s[i] == '0')      ++sum;
            else if (s[i] == '1') --sum;
            max_sum = max(max_sum, sum);
        }

        return max_sum;
    }
};
```
**Explanation:**
	Цель: Дана строка, нужно найти максимальуную суммму, такую что строка делится на две непустые подстроки. слеа считается полукичество нулей, справа количество едениц.
	Решение: Посчиать количество едениц в строке. Проходится слева на право прибавляя нули и вычтая еденицы. Вернуть максимальную сумму.