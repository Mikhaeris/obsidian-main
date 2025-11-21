**Complexity:** Easy
Answer:
	Time Complexity: O(N+M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countNegatives(vector<vector<int>>& grid) {
        int rows = grid.size();

        int row = 0; 
        int col = grid[0].size()-1;
        int count = 0;

        while (row < rows && col >= 0) {
            if (grid[row][col] < 0) {
                count += rows-row;
                col--;
            } else {
                row++;
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дана отсортированая матрица. Требуется узнать сколько в ней отрицательных числе.
	Решение: так как матрица отсортированная, то можно не считать все элементы. Проходится с правого верхнего угла до левого нижнего. Если данное число меньше нуля, то все числа в этом столбце тоже меньше нуля, значит можно прибавить весь столбец. Если число больше нуля, знаит нужно идти вниз(т.е. прибавить строку). Выход из цикла, когда строка становится равна размеру строку в матрице и если колонка становится меньше нуля.