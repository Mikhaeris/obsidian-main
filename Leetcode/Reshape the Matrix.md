**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<vector<int>> matrixReshape(vector<vector<int>>& mat, int r, int c) {
        int old_r = mat.size(), old_c = mat[0].size();
        if (old_r * old_c != r * c) {
            return mat;
        }

        vector<vector<int>> ans(r, vector<int>(c));
        for (int i = 0; i < r * c; i++) {
            ans[i / c][i % c] = mat[i / old_c][i % old_c];
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дана матрица размером a на b, нужно изменить размерность матрицы на r и c, если невозможно, то вернуть исхожную матрицу.
	Pешение: Проверить на правильность. Изменить размерность матрицы