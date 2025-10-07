**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N\*2)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        int n; cin >> n;
        vector<vector<char>> matrix(n*2, vector<char>(n*2));
        int ci = 0;
        for (int i = 0; i < matrix.size(); ++i) {
            int cj = 0;
            for (int j = 0; j < matrix.size(); ++j) {
                if (((ci & 1) == 0) && ((cj & 1) == 0)) {
                    matrix[i][j] = '#';
                } else if (((ci & 1) == 1) && ((cj & 1) == 1)) {
                    matrix[i][j] = '#';
                } else {
                    matrix[i][j] = '.';
                }

                if (j & 1) {
                    ++cj;
                }
            }
            if (i & 1) {
                ++ci;
            }
        }

        for (const auto& vec : matrix) {
            for (const auto& el : vec) {
                cout << el;
            }
            cout << '\n';
        }
        cout.flush();
    }
    return 0;
}
```
**Explanation:**
	Цель: Нужно сделать чередующиеся решетки и точки, сгруппированные по два элемента.
	Решение: Идти по матрице с помощью дополнительных индексов, которые увеличиваются каждые два отсчета.