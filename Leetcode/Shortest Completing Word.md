**Complexity:** Easy
Answer:
	Time Complexity: O(N+N^(M+N))
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    string shortestCompletingWord(string licensePlate, vector<string>& words) {
        int req[26] = {0};
        for (const auto& ch : licensePlate) {
            if (isalpha(ch)) {
                ++req[tolower(ch) - 'a'];
            }
        }

        string ans = "";
        for (const auto& w : words) {
            int tmp[26] = {0};
            for (const auto& ch : w) {
                ++tmp[ch - 'a'];
            }

            for (int i = 0; i < 26; ++i) {
                if (tmp[i] < req[i]) {
                    goto skip;
                }
            }

            if ((ans.empty()) || (w.size() < ans.size())) {
                ans = w;
            }
            skip:
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дано слово и массив слов. Нужно найти такое слово минимальной длины, которое, будет содержат все буквы из данного слова.
	Pешение: Составить масссив количества букв в данном слове. И потом делать тоже самое для каждого слова и проверять их валидность.
