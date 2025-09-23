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
        int n, a, b;
        cin >> n >> a >> b;

        if (b > 2 * a) {
            cout << n * a << endl;
            continue;
        }

        int ans = 0;
        ans += (n / 2) * b;
        ans += (n % 2) * a;
        cout << ans << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дано количство йогуртов, который нужно купить. Стоимост
	Решение: Считывать первую строку, изменяя B на G. Считывать сторую строку и проверять ее сходство с первой. Вывести ответ.