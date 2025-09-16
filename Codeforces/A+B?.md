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
    cin.ignore();
    for (int i = 0; i < t; ++i) {
        int sum = 0;
        char c = 0;
        while ((c = getchar()) != '\n') {
            if (c != '+') {
                sum += c - '0';
            }
        }
        cout << sum << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка a+b, нужно вернуть сумму a + b.
	Решение: Просто складывать и возвращать сумму.