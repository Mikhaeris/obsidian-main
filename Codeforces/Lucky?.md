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

int main () {
    int t; cin >> t;
    for (int i = 0; i< t; i++) {
        string s; cin >> s;
        int l = s[5] - '0' + s[4] - '0' + s[3] - '0';
        int r = s[2] - '0' + s[1] - '0' + s[0] - '0';
        if (l == r) {
            cout << "YES" << endl;
        } else {
            cout << "NO" << endl;
        }
    }
    return 0;
}

```
**Explanation:**
	Цель: Узнать является ли билет счастливым. Счистливый билет, тот в коттором сумма правой части равняется сумме левой части.
	Решение: Посчитать суммы и сравнить.