**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> getRow(int rowIndex) {
        vector<int> prev;
        for (int i = 1; i < rowIndex+2; ++i) {
            vector<int> curr;
            for (int j = 0; j < i; ++j) {
                if (j == 0 || j == i-1) {
                    curr.push_back(1);
                }
                else {
                    curr.push_back(prev[j-1] + prev[j]);
                }
            }
  
            prev = curr;
        }
  
        return prev;
    }
};
```
**Explanation:**
	Цель: Дано число. Нужно вернуть этот ряд треугольника Паскаля
	Решение: Сохранять последний и нынешний.
