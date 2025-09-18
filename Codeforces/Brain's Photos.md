**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int n, m; cin >> n >> m;
    char c;
    bool flag = true;
    for (int i = 0; i < n; ++i) {
        for (int j = 0; j < m; ++j) {
            cin >> c;
            if (c != 'W' && c != 'G' && c != 'B') {
                flag = false;
            }

        }
    }

    if (flag) {
        cout << "#Black&White" << endl;
    } else {
        cout << "#Color" << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана фотография (в виде матрицы цветов), нужно узнать цветная или черно-белая она.
	Решение: Если в фотографии есть цветный цвета, то в вывести что она цветная, иначе она черно-белая.