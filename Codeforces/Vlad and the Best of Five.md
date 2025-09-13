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
        int x, n; cin >> x >> n;
        (n & 1)
        ? cout << x << endl
        : cout << 0 << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: D 
	Решение: 24 - (h + 1) - т.е. скольок часов осталось минус этот до нового года умноженное на 60 плюс 60 - данное колиество минут.