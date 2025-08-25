**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool satisfiesConditions(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();
        for(int i=0; i<m; i++){
            for(int j=0; j<n; j++){
                if(i+1 < m && grid[i][j] != grid[i+1][j])
                    return false;
                if(j+1 < n && grid[i][j] == grid[i][j+1])
                    return false;
            }
        }
        return true;
    }
};
```
**Explanation:**
	Цель: Дана матрица, в ней нужно проверить, что в столбце все элеенты равны, в строке они все разные.
	Решение: Сначала проверям первую строку, потом проверям каждую колонку.