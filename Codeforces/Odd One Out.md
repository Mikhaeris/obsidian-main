**Complexity:** 800
Answer:
	Time Complexity: O(count_bit)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main () {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int f, s, t; cin >> f >> s >> t;
        if (f != s && f != t && s == t) {
            cout << f << endl;
        } else if (s != f && s != t && f == t) {
            cout << s << endl;
        } else {
            cout << t << endl;
        }
    }
    return 0;
}
```
**Explanation:**
	Цель: Даны три числа, нужно вывести число, которое отличается от двух других.
	Решение: Просто вывести отличающееся число.