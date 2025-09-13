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
        int count = 0;
        char c;
        while ((c = getchar()) != '\n') {
            (c == 'A') ? ++count : --count;
        }

        cout << ((count > 0) ? 'A' : 'B') << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка из 5 символов. Нужно азнуть каких символов больше 'A' или 'B'.
	Решение: Один счетчик увеличивается и уменьшается.