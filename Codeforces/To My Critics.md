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
    for (int i = 0; i < t; i++) {
        int a, b, c;
        cin >> a >> b >> c;
        if (a+b >= 10 || a+c >= 10 || b+c >= 10) {
            cout << "YES" << endl;
        } else {
            cout << "NO" << endl;
        }
    }

    return 0;
} 
```
**Explanation:**
	Цель: Даны три числа, нужно узнать, можно ли сложив два любых числа из данных получить число больше или равное десяти.
	Решение: Получать числа и проверять.