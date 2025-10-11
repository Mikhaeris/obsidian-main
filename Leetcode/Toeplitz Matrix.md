**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    bool isToeplitzMatrix(vector<vector<int>>& matrix) {
        for (int i = 0; i < matrix.size()-1; ++i) {
            for (int j = 0; j < matrix[0].size()-1; ++j) {
                if (matrix[i][j] != matrix[i+1][j+1]) {
                    return false;
                }
            }
        }
        return true;
    }
};
```
**Explanation:**
	Цель: Нужно проверить, что матрица тополизировна, это такая матрица, в которой элементы в каждй диагонали равны.
	Pешение: Проверять элементы i и j, i+1 и j+1. если они не равны, то вернуть false.