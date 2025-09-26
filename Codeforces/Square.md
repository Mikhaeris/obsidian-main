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
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int a, b; cin >> a >> b;
        int f = a, s = 0;
        for (int j = 0; j < 3; ++j) {
            cin >> a >> b;
            if (a != f && a != b) {
                s = a;
            }
        }
        cout << ((f - s) * (f - s)) << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Даны точки квадрата, сотороны которого параеленьны осям координат. Требуется узнать площадь этого квадрата.
	Решение: Взять две отличные точик по оси x. вычислить между ними разницу и возвести в квадрат.