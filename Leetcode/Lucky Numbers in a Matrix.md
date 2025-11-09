**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> luckyNumbers(vector<vector<int>>& matrix) {
        for (int i = 0; i < matrix.size(); ++i) {
            int min_n = matrix[i][0], pos = 0;
            for (int j = 0; j < matrix[i].size(); ++j) {
                if (matrix[i][j] < min_n) {
                    min_n = matrix[i][j];
                    pos = j;
                }
            }


            for (int j = 0; j < matrix.size(); ++j) {
                if (matrix[j][pos] > min_n) {
                    goto skip;
                }
            }

            return {min_n};
			skip:
        }

        return {};
    }
};
```
**Explanation:**
	Цель: Дана матрица m на n, нужно найти счастливое число. Счастливое число - это такое число, которое макимальное в столбце, но минимаьное в строке.
	Решение: Проходится по матрце и в строках искать минимальное число. Дальше проверять что это число максимальное в столбце, если это не так, то перейти к следующей итерации, иначе вернуть это число.
	P.S. Тут можно доказать, что такое число существует только одно.