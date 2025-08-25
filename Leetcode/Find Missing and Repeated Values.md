**Complexity:** Easy
Answer:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> findMissingAndRepeatedValues(vector<vector<int>>& grid) {
        vector<int> vec(grid.size()*grid.size());
        for (int i = 0; i < grid.size(); ++i) {
            for (int j = 0; j < grid[i].size(); ++j) {
                ++vec[grid[i][j]-1];
            }
        }
  
        int repeat = 0, absence = 0;
        for (int i = 0; i < vec.size(); ++i) {
            if (vec[i] == 2) {
                repeat = i+1;
            }
            if (vec[i] == 0) {
                absence = i+1;
            }
        }
  
        return {repeat, absence};
    }
};
```
**Explanation:**
	Цель: Дана матрица рамерностью n\*n, в ней содержатся числа от 1 до n, нужно натйи повторябщее число и вернуть повторяющее плюс отсутствуешее.  
	Решение: Собрать все числа в массив по количеству их повторений, так как от 1 до n, и потом посмотреть, которое повторяется, и котоорое отсутсвтует.
