**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        int n; cin >> n;

        int m1 = 0, m2 = 0;
        vector<int> vec(n);
        for (int i = 0; i < n; ++i) {
            cin >> vec[i];

            if (vec[i] > m1) {
                m2 = m1;
                m1 = vec[i];
            } else if (vec[i] > m2) {
                m2 = vec[i];
            }
        }

        for (int i = 0; i < n; ++i) {
            if (vec[i] == m1) {
                cout << m1 - m2 << ' ';
            } else {
                cout << vec[i] - m1 << ' ';
            }
        }
        cout << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Даны силы i-х участников, нужно узнать различие сил для каждого с максимальным, не включая его самого.
	Решение: Узнать силы двух макисимальных участников. Для каждого узнать разнцу с максимальным, для максимального узнать разницу со вторым максимальным.