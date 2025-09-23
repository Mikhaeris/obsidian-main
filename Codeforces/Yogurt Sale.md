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
	Цель: Дано количство йогуртов, который нужно купить. Стоимость одного йогрурта, стоимость двух йогуртов по акции.
	Решение: Проверить что акциия выгодна, иначе просто купить n йогуртов за a бурлей. Если акция выгодна, то посчитать йогруты по скидки, и если есть то один завершающий йогурт.