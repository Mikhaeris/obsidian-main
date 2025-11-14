**Complexity:** Medium
Answer:
	Time Complexity: O(M*\N\^2)
	Space Complexity: O(N^2)
Code:
Solution:
```cpp
class Solution {
public:
    vector<vector<int>> rangeAddQueries(int n, vector<vector<int>>& queries) {
        vector<vector<int>> matrix(n, vector<int>(n, 0));
        for (const auto& req : queries) {
            for (int i = req[0]; i <= req[2]; ++i) {
                for (int j = req[1]; j <= req[3]; ++j) {
                    matrix[i][j] += 1;
                }
            }
        }
        return matrix;
    }
};
```
**Explanation:**
	Цель: Дан размер матрицы n на n. И массив запросов, где каждый запрос увеличивает подматрицу на один. Нужно вернуь окончательную матрицу.
	Решение: Проходится по каждому запросу и увеличивать подматрицу на один.
	P.S.  Это плохое решение. Нужно решать через сумму префиксов для матрицы, заполнив так запросы и потом пройтись по матрице прфексов и увеличивать нужные клктки в матрице на нужные значения.