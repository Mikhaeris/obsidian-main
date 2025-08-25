**Complexity:** Medium
**Task:**
	En: Given an `m x n` integer matrix `matrix`, if an element is `0`, set its entire row and column to `0`'s.
	You must do it [in place](https://en.wikipedia.org/wiki/In-place_algorithm).
	Ru: Дана целочисленная матрица `matrix` размера m × n; если какой-то элемент равен 0, заполнить нулями всю его строку и столбец.
	Необходимо выполнить это на месте.
	
**Example:**
	**Example 1:**
		![](https://assets.leetcode.com/uploads/2020/08/17/mat1.jpg)
		**Input:** matrix = [ [1,1,1],[1,0,1],[1,1,1] ]
		**Output:** [ [1,0,1],[0,0,0],[1,0,1] ]
	**Example 2:**
		![](https://assets.leetcode.com/uploads/2020/08/17/mat2.jpg)
		**Input:** matrix = [ [0,1,2,0],[3,4,5,2],[1,3,1,5] ]
		**Output:** [ [0,0,0,0],[0,4,5,0],[0,3,1,0] ]

**Constraints:**
	`m == matrix.length`
	`n == matrix[0].length`
	`1 <= m, n <= 200`
	`-231 <= matrix[i][j] <= 231 - 1`
	
Answer:
	Time Complexity: O(n+m+n)
	Space Complexity: O(2n)
Code:
Solution 1:
```cpp
class Solution {
public:
   void setZeroes(vector<vector<int>>& matrix) {
		vector<vector<int>> dopMatrix = matrix;
	
		for (int i = 0; i < matrix.size(); ++i) {
			for (int j = 0; j < matrix[0].size(); ++j) {
				if (matrix[i][j] == 0) {
					for (int k = 0; k < matrix[0].size(); ++k) {
						dopMatrix[i][k] = 0;
					}
					for (int k = 0; k < matrix.size(); ++k) {
						dopMatrix[k][j] = 0;
					}
				}
			}
		}
	
		for (int i = 0; i < matrix.size(); ++i) {
			for (int j = 0; j < matrix[0].size(); ++j) {
				if (dopMatrix[i][j] == 0) {
					matrix[i][j] = 0;
				}
			}
		}
	}
};
```
Answer:
	Time Complexity: O(n+n)
	Space Complexity: O(1)
Solution 2:
```cpp
class Solution {
public:
	void setZeroes(vector<vector<int>>& matrix) {
		bool flag = false;
		for (int i = 0; i < matrix.size(); ++i) {
			if (matrix[i][0] == 0) flag = true;
			for (int j = 1; j < matrix[i].size(); ++j) {
				if (matrix[i][j] == 0) {
					matrix[i][0] = 0;
					matrix[0][j] = 0;
				}
			}
		}
		
		for (int i = matrix.size()-1; i >= 0; --i) {
			for (int j = matrix[0].size()-1; j >= 0; --j) {
				if (matrix[i][0] == 0 || matrix[0][j] == 0) {
					matrix[i][j] = 0;
				}
			}
			if (flag) {
				matrix[i][0] = 0;
			}
		}
	}
};
```
**Explanation:**
	Цель: В матрице есть нули, нужно продлить их по столбцам и по строкам
	Решение 1: Создать копию первой матрицы.
	Проходится по основной матрице и если ноль, то в дополнительной изменять столбцы и строки на ноль для данной позиции.
	В конце проицировать дополнительную матрицу на основную. 
	Решение 2:
	Если встречается ноль, то установка заметок по краям(слева и сверху).
	После прохождение с обратной стороны и проверка на заметки(если есть сверху или слева), то установка в данной ячейке нуля.
	Это решение является правильным по условию задачи(проводить все операции в данном объекте).