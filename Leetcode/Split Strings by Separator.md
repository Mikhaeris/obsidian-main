**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<string> splitWordsBySeparator(vector<string>& words, char separator) {
        vector<string> ans; string temp = "";
        for (const auto& word : words) {
            for (const auto& ch : word) {
                if (ch == separator) {
                    if (!temp.empty()) {
                        ans.push_back(temp);
                    }
                    temp = "";
                } else {
                    temp += ch;
                }
            }
            if (!temp.empty()) {
                ans.push_back(temp);
            }
            temp = "";
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив строк с разделителями, нужно каждую строку раздеить на слова через разделитель.
	Решение: Добавлять символы в временную строку и потом при в конце строки или при встрече разделителя добавлять в конечный массив.