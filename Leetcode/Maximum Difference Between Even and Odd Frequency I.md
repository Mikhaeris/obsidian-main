**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxDifference(string s) {
        unordered_map<char, int> map;
        for (const auto& c : s) {
            ++map[c];
        }
  
        int odd_max = 0, even_max = INT_MAX;
        for (const auto& pair_s : map) {
            if (pair_s.second % 2) {
                if (odd_max < pair_s.second) {
                    odd_max = pair_s.second;
                }
            }
            else {
                if (even_max > pair_s.second) {
                    even_max = pair_s.second;
                }
            }
        }
  
        return odd_max - even_max;
    }
};
```
**Explanation:**
	Цель: Дана строка символов, нужно найти в ней макисмальнуюб разницу между количество мповторений нечетных и четных чисел.
	Решение: Составить [[Hash table]] хэш-таблицу, в которой будет хранится количество повторений символов. Потом пройтись и искать максимальное нечетное и минимальное четное число. В конце вычесть из нечетного четное и получится ответ.