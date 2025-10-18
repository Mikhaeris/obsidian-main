**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <string>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        string move; cin >> move;
        for (int i = 0; i < 8; ++i) {
            if (i + 'a' != move[0]) {
                char ch = i + 'a';
                cout << ch << move[1] << '\n';
            }
        }
        for (int i = 0; i < 8; ++i) {
            if (i + 1 != move[1] - '0') {
                cout << move[0] << i+1 << '\n';
            }
        }
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Дана позиция ладьи, нужно узнать все позиции куда ладья может сходить.
	Решение: Проходится по горизонтали и по диагонали, пропуская текущую позицию ладьи.