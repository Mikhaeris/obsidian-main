**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int numSub(string s) {
        static constexpr int mod = int(1E9) + 7;
        int ans = 0;
        int curr = 0;
        for (const auto& ch : s) {
            if (ch == '1') {
                ++curr;
                ans = (ans + curr) % mod;
            } else {
                curr = 0;
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дана строка из нулей и едениц. Нужно посчитать все подстроки, в которых есть еденицы.
	Решение: Считать количество едениц, если ноль, то обнулять счетчик. Кажый раз, когда есть еденица, прибавлять к количеству подстрок текущее количество едениц(это как бы и будет количество всех подстрок). Прибавлять по модулю.