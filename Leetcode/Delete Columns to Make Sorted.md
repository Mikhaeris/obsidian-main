**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minDeletionSize(vector<string>& strs) {
        int count = 0;
        for (int i = 0; i < strs[0].size(); ++i) {
            for (int j = 0; j < strs.size()-1; ++j) {
                if (strs[j][i] > strs[j+1][i]) {
                    ++count;
                    break;
                }
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дан массив строк одинаковой длины. Требуется узнать сколько столбоцов нужно удалить, чтобы все столбцы были отсортированы лексикографически.
	Pешение: Проходится по столбцам(т.е. от длины одного слова по количеству слов) и проверять, что текущая буква меньше следующей, иначе прибавить к счетчику и перейти к следующему столбцу.