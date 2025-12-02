**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
public:
    vector<int> recoverOrder(vector<int>& order, vector<int>& friends) {
        unordered_set<int> st;
        for (const auto& f : friends) {
            st.insert(f);
        }

        vector<int> ans;
        for (const auto& n : order) {
            if (st.find(n) != st.end()) {
                ans.push_back(n);
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан два массива, первый позиция каждого индекса на финише, второй индексу друзей. Нужно вернуть массив из индексов друзей в котором они пришли на финиш.
	Решение: Сохранить друзей в хеш таблицу. Проверять если этот индекс в хеш таблице и если есть, то добавить в массив ответа. Вернуть массив.