**Complexity:** 800
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int n, m, k;
    cin >> n >> m >> k;
    if (n > m || n > k) {
        cout << "NO" << endl;
    } else {
        cout << "YES" << endl;
    }
}
```
**Explanation:**
	Цель: Проверить что число n меньше m и k.
	Решение: Просто проверить.