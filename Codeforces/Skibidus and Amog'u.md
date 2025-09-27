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
        string w; cin >> w;
        cout << (string(w.begin(), w.begin() + (w.length() - 2)) + 'i') << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Преобразовать слово из единственного числа в множестунное число.
	Решение: Менять две последние буквы на 'i'.