**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        string a; cin >> a;
        string b = "";
        for (int j = a.length()-1; j >= 0; --j) {
            if (a[j] == 'p') {
                b += 'q';
            } else if (a[j] == 'q') {
                b += 'p';
            } else {
                b += 'w';
            }
        }
        cout << b << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка, нужно ее отзеркалить.
	Решение: Проходится с конца и зеркалить строку.