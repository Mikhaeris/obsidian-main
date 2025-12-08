**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countTriples(int n) {
        unordered_set<int> st;
        for (int i = 1; i <= n; ++i) {
            st.insert(i * i);
        }

        int count = 0;
        for (int i = 1; i <= n; ++i) {
            for (int j = 1; j <= n; ++j) {
                int res = i * i + j * j;

                if (st.find(res) != st.end()) {
                    ++count;
                }
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно найти все такие комбинации, которые будут давать квадратные тройки, где a^2 + b^2 = c^2.
	Pешение: Просто перебрать все возможные варианты.