**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int countConsistentStrings(string& allowed, vector<string>& words) {
        unordered_set<char> st;
        for (const auto& ch : allowed) {
            st.insert(ch);
        }

        int count = 0;
        for (const auto& str : words) {
            bool flag = true;
            for (const auto& ch : str) {
                if (st.find(ch) == st.end()) {
                    flag = false;
                    break;
                }
            }

            if (flag) {
                ++count;
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель:  Дана строка с правильными символами. Проверить, что слова в массиве состоят только из праивльных символов.
	Решение: Сохрнаить все правильные символы в хеш таблице. Проверять содержатся ли буквы из слова в праивльных буквах, елси нет то не засчитывать слово.