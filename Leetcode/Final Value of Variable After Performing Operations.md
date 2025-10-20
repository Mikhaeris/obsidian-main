**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int finalValueAfterOperations(vector<string>& operations) {
        int x = 0;
        for (const auto& oper : operations) {
            if (oper[0] == '+' || oper[2] == '+') {
                ++x;
            } else {
                --x;
            }
        }
        return x;
    }
};
```
**Explanation:**
	Цель: В языке существует всего две опреации ++X, X++, --X, X--, нужно узнать чему будте равна переменная X после всех операций.
	Решение: Узнавать тип операции(либо в начале, либо в конце). Вывести результат