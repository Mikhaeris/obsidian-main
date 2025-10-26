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
    int n; cin >> n;
    
    bool flag = false;
    if ((n % 10) >= 5) { flag = true; }

    n /= 10;
    n *= 10;
    if (flag) {
        n += 10;
    }

    cout << n << endl;
    return 0;
}
```
**Explanation:**
	Цель: Округлить число по правилам математики.
	Решение: Проверить чему равно последнее число и в зависимости от этого округлить вврех или вниз.