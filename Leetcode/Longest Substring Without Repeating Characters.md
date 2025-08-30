**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int alph[96] = {0};
        int max_l = 0;

        int l = 0, r = 0;
        while (r < s.length()) {
            alph[s[r]-' ']++;

            if (alph[s[r]-' '] > 1) {
                max_l = max(max_l, r-l);

                while (alph[s[r]-' '] != 1) {
                    alph[s[l]-' ']--;
                    l++;
                }
            }
            r++;
        }
        max_l = max(max_l, r-l);

        return max_l;
    }
};
```
**Explanation:**
	Цель: Дана строка. Нужно найти такую самую длинную подстроку, в которой си
	Решение: N раз совершать оперцию над каждым числом последовательности. Вернуть получившееся число.