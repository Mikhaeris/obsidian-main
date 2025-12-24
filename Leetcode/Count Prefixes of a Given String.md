**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countPrefixes(vector<string>& words, string s) {
        int count = 0;
        for (const auto& w : words) {
            if (w.size() > s.size()) {
                continue;
            }

            for (int i = 0; i < w.size(); ++i) {
                if (w[i] != s[i]) {
                    goto skip;
                }
            }
            ++count;
            skip:
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дана строка и массив возможных префиксов. Нужно узант сколько префиксов являются верными.
	Pешение: Фактически задача состоит в проверки подстроки в строке, нго начиная с начала. Т.е. нужно просто проверить что первая часть префиска равняется части строки.