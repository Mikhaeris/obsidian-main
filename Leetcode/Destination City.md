**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string destCity(vector<vector<string>>& paths) {
        unordered_set<string> st;
        for (const auto& p : paths) {
            st.insert(p[0]);
        }

        for (const auto& p : paths) {
            if (st.find(p[1]) == st.end()) {
                return p[1];
            }
        }

        return {};
    }
};
```
**Explanation:**
	Цель: Дан массив путей из города в город. Нужно найти такой город, из которого нет пути.
	Pешение: Сохранить все города из которых идут пути в хеш таблицу. Дальше пройтись по городам в которые идут пути и проверять есть ли они в хеш таблице, если нет, то вернуть этот город.