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
    do {
        int a, b, c;
        cin >> a >> b >> c;
        if (a < b && b < c) {
            cout << "STAIR" << endl;
        } else if (a < b && b > c) {
            cout << "PEAK" << endl;
        } else {
            cout << "NONE" << endl;
        }
    } while (--t);
    return 0;
}
```
**Explanation:**
	Цель: Узнать что это: лестница, пик или ничего.
	Решение: Проверить и вывести результат.