**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int numJewelsInStones(string jewels, string stones) {
        unordered_set<char> st;
        for (const auto& c : jewels) {
            st.insert(c);
        }

        int count = 0;
        for (const auto& c : stones) {
            if (st.find(c) != st.end()) {
                ++count;
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Даны драгоценные камни и кучка камней. Нужно узнать сколько камней из кучки являются драгоценными.
	Pешение: Записать все драгоценные камни в сет. Пройтись по камням из кучки и проверить, если ли они в сете, если есть то прибавлять к количеству один.
