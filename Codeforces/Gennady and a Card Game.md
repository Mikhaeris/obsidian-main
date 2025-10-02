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
    string m; cin >> m;
    
    bool flag = false;
    string temp;
    for (int i = 0; i < 5; ++i) {
        cin >> temp;
        if (m[0] == temp[0] || m[1] == temp[1]) {
            flag = true;
        }
    }
    cout << ((flag) ? "YES" : "NO") << endl;
    return 0;
}
```
**Explanation:**
	Цель: На столе карта, на руках 5 карт. Нужно узнать, можно ли сходить какой-либо картой.
	Решение: Проверить первую часть и вторую часть каждой карты.