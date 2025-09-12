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
        int h, m; cin >> h >> m;

        cout << ((24 - (h + 1)) * 60) + (60 - m) << endl;

    }
    return 0;
}
```
**Explanation:**
	Цель: Дано два числа - часы и минуты. Нужно узнать сколько минут осталось до нового года.
	Решение: 24 - (h + 1) - т.е. скольок часов осталось минус этот до нового года умноженное на 60 плюс 60 - данное колиество минут.