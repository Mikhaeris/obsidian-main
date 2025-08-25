**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <algorithm>
#include <iostream>

using namespace std;

int main () {
    int n; cin >> n;

    int sum = 0, max_el = -1;
    for (int i = 0; i < n; ++i) {
        int num; cin >> num;
        sum += num;

        max_el = max(max_el, num);
    }

    cout << (max_el*n)-sum << endl;

    return 0;
}
```
**Explanation:**
	Цель: Дан N чисел, нужно узнать сколкьо всего нужно прибавить ко всем числам, чтобы каждое число было равно каждому.
	Решение: Посчитать сумму чисел и найти максимлаьное число. Равная сумма будет у всех, когда каждое число приравнять к максимальному, следоавтельно нужно просто из максимальной суммы вычесть текущую и это и будте ответ.